Install
=============

.. toctree::
    :maxdepth: 4

Install using PyPI
------------------

.. code:: bash

   # bash
   pip install substrate-interface

Initialization
--------------

.. code:: python

   portaldot = SubstrateInterface(
      url="wss://mainnet.portaldot.io",
      ss58_format=42,
      type_registry_preset='default'
   )

If connecting to a local node, ``url`` should be setting as 

.. code:: python

   url="ws://127.0.0.1:9944"


Quick usage
-----------

**Balance information of an account**

.. code:: python

   result = portaldot.query('System', 'Account', ['5E9oDs9PjpsBbxXxRE9uMaZZhnBAV38n2ouLB28oecBDdeQo'])
   print(result.value['data']['free']) # 635278638077956496

**Create balance transfer extrinsic**

.. code:: python

   call = portaldot.compose_call(
       call_module='Balances',
       call_function='transfer_keep_alive',
       call_params={
           'dest': '5E9oDs9PjpsBbxXxRE9uMaZZhnBAV38n2ouLB28oecBDdeQo',
           'value': 1 * 10**12
       }
   )
   keypair = Keypair.create_from_uri('//Alice')
   extrinsic = portaldot.create_signed_extrinsic(call=call, keypair=keypair)
   receipt = portaldot.submit_extrinsic(extrinsic, wait_for_inclusion=True)

   print(f"Extrinsic '{receipt.extrinsic_hash}' sent and included in block '{receipt.block_hash}'")
