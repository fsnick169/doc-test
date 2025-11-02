Extrinsics
==========

.. toctree::
   :maxdepth: 4

In Portaldot, transactions are often more broadly referred to as
(signed) extrinsics. The term extrinsic is generally used to mean any
information that originates outside of the runtime. An extrinsic is
basically a vehicle that carries the intention to execute a function
call in the runtime, along with proof of the account that wants to
execute it.

**Creating extrinsics**

*Example:*

.. code:: python

   call = portaldot.compose_call(
       call_module='Balances',
       call_function='transfer_keep_alive',
       call_params={
           'dest': '5E9oDs9PjpsBbxXxRE9uMaZZhnBAV38n2ouLB28oecBDdeQo',
           'value': 1 * 10** 14
       }
   )

   extrinsic = portaldot.create_signed_extrinsic(call=call, keypair=keypair)

   try:
       receipt = portaldot.submit_extrinsic(extrinsic, wait_for_inclusion=True)
       print(f"Extrinsic '{receipt.extrinsic_hash}' sent and included in block '{receipt.block_hash}'")

   except SubstrateRequestException as e:
       print("Failed to send: {}".format(e))

The ``wait_for_inclusion`` keyword argument used in the example above
will block giving the result until it gets confirmation from the node
that the extrinsic is succesfully included in a block. The
``wait_for_finalization`` keyword will wait until extrinsic is
finalized. Note this feature is only available for websocket
connections.

**Extrinsic Receipts**

The ``portaldot.submit_extrinsic()`` example above returns an
``ExtrinsicReceipt`` object, which contains information about the
on-chain execution of the extrinsic. Because the ``block_hash`` is
necessary to retrieve the triggered events from storage, most
information is only available when ``wait_for_inclusion=True`` or
``wait_for_finalization=True`` is used when submitting an extrinsic.

Examples:

.. code:: python

   receipt = portaldot.submit_extrinsic(extrinsic, wait_for_inclusion=True)
   print(receipt.is_success) # False
   print(receipt.weight)
   print(receipt.total_fee_amount)
   print(receipt.error_message['name']) # 'LiquidityRestrictions'

``ExtrinsicReceipt`` objects can also be created for all existing
extrinsics on-chain:

.. code:: python


   receipt = portaldot.retrieve_extrinsic_by_identifier("5233297-1")

   print(receipt.is_success)
   print(receipt.extrinsic.call_module.name)
   print(receipt.extrinsic.call.name)
   print(receipt.weight)
   print(receipt.total_fee_amount)
   print(receipt.error_message['docs'])

   for event in receipt.triggered_events:
       print(f'* {event.value}')

**Multisig extrinsics**

Substrate has the functionality for multi-signature dispatch, allowing
multiple signed origins (accounts) to coordinate and dispatch a call,
derivable deterministically from the set of account IDs and the
threshold number of accounts from the set that must approve it.

To initiate and finalize multisig extrinsics, the following helper
functions are available:

*Define the multisig account by supplying its signatories and
threshold:*

.. code:: python

   keypair_alice = Keypair.create_from_uri('//Alice', ss58_format=portaldot.ss58_format)

   multisig_account = portaldot.generate_multisig_account(
       signatories=[
           keypair_alice.ss58_address, 
           '5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty', 
           '5FLSigC9HGRKVhB9FiEo4Y3koPsNmBmLJbpXg2mp1hXcS59Y'
       ], 
       threshold=2
   )

*Then initiate the multisig extrinsic by providing the call and a
keypair of one of its signatories:*

.. code:: python

   call = portaldot.compose_call(
       call_module='System',
       call_function='remark_with_event',
       call_params={
           'remark': 'Multisig test'
       }
   )

   extrinsic = portaldot.create_multisig_extrinsic(call, keypair_alice, multisig_account, era={'period': 64})
   receipt = portaldot.submit_extrinsic(extrinsic, wait_for_inclusion=True)

*Then a second signatory approves and finalizes the call by providing
the same call to another multisig extrinsic:*

.. code:: python

   # Define the multisig account by supplying its signatories and threshold
   keypair_charlie = Keypair.create_from_uri('//Charlie', ss58_format=portaldot.ss58_format)

   multisig_account = portaldot.generate_multisig_account(
       signatories=[
           keypair_charlie.ss58_address, 
           '5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY', 
           '5FLSigC9HGRKVhB9FiEo4Y3koPsNmBmLJbpXg2mp1hXcS59Y'
       ], 
       threshold=2
   )

   extrinsic = portaldot.create_multisig_extrinsic(call, keypair_charlie, multisig_account, era={'period': 64})
   receipt = portaldot.submit_extrinsic(extrinsic, wait_for_inclusion=True)

The call will be executed when the second and final multisig extrinsic
is submitted, condition and state of the multig will be checked on-chain
during processing of the multisig extrinsic.

**Type decomposition of call params**

The structure of certain call parameters can be quite complex, then the
``get_param_info()`` function of the call function object can provide
more insight how to construct those parameters:

.. code:: python

   call_function = portaldot.get_metadata_call_function("POT", "transfer")
   param_info = call_function.get_param_info()

**Estimate of network fees**

.. code:: python

   payment_info = portaldot.get_payment_info(call=call, keypair=keypair)

**Mortal extrinsics**

By default, *immortal* extrinsics are created, which means they have an
indefinite lifetime for being included in a block. However, it is
recommended to use specify an expiry window, so you know after a certain
amount of time if the extrinsic is not included in a block, it will be
invalidated.

.. code:: python

   extrinsic = portaldot.create_signed_extrinsic(call=call, keypair=keypair, era={'period': 64})

The ``period`` specifies the number of blocks the extrinsic is valid
counted from current head.

