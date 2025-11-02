ink! contract interfacing
=========================

.. toctree::
   :maxdepth: 4

ink! is a programming language for smart contracts; blockchains built
with the Substrate framework can choose from a number of smart contract
languages which one(s) they want to support. ink! is one of them. It is
an opinionated language that we have built by extending the popular Rust
programming language with functionality needed to make it smart contract
compatible.

`More information about ink! <https://use.ink/>`__

**Deploy a contract**

.. code:: python

   portaldot = SubstrateInterface(
         url="wss://mainnet.portaldot.io",
         ss58_format=42,
         type_registry_preset='default'
      )

   keypair = Keypair.create_from_uri('//Alice')

   # Deploy contract
   code = ContractCode.create_from_contract_files(
       metadata_file=os.path.join(os.path.dirname(__file__), 'assets', 'test_contract.json'),
       wasm_file=os.path.join(os.path.dirname(__file__), 'assets', 'test_contract.wasm'),
       substrate=substrate
   )

   contract = code.deploy(
       keypair=keypair,
       endowment=0,
       gas_limit=1000000000000,
       constructor="new",
       args={'init_value': True},
       upload_code=True
   )

   print(f'Deployed @ {contract.contract_address}')

**Work with an existing instance:**

.. code:: python

   # Create contract instance from deterministic address
   contract = ContractInstance.create_from_address(
       contract_address=contract_address,
       metadata_file=os.path.join(os.path.dirname(__file__), 'assets', 'test_contract.json'),
       substrate=substrate
   )

**Read data from a contract:**

.. code:: python

   result = contract.read(keypair, 'get')
   print('Current value of "get":', result.contract_result_data)

**Execute a contract call**

.. code:: python

   # Do a gas estimation of the message
   gas_predit_result = contract.read(keypair, 'flip')

   print('Result of dry-run: ', gas_predit_result.value)
   print('Gas estimate: ', gas_predit_result.gas_required)

   # Do the actual call
   print('Executing contract call...')
   contract_receipt = contract.exec(keypair, 'flip', args={

   }, gas_limit=gas_predit_result.gas_required)

   if contract_receipt.is_success:
       print(f'Events triggered in contract: {contract_receipt.contract_events}')
   else:
       print(f'Error message: {contract_receipt.error_message}')

