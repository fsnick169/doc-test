Call runtime APIs
=================

.. toctree::
   :maxdepth: 4

A Portaldot node contains a runtime. The runtime contains the business
logic of the chain. It defines what transactions are valid and invalid
and determines how the chain’s state changes in response to
transactions.

**Example**

.. code:: python

   result = portaldot.runtime_call("AccountNonceApi", "account_nonce", ["5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY"])
   # <U32(value=2)>

**List of available runtime APIs and methods**

.. code:: python

   runtime_calls = portaldot.get_metadata_runtime_call_functions()
   #[
   #    <RuntimeCallDefinition(value={'description': 'The API to query account nonce (aka transaction index)', 'params': [{'name': 'account_id', 'type': 'AccountId'}], 'type': 'Index', 'api': 'AccountNonceApi', 'method': 'account_nonce'})>
   #    ...
   #]

**Get param type decomposition**

A helper function to compose the parameters for this runtime API call

.. code:: python

   runtime_call = portaldot.get_metadata_runtime_call_function("ContractsApi", "call")
   param_info = runtime_call.get_param_info()
