Query storage
=============

.. toctree::
   :maxdepth: 4

In Portaldot, any pallet can introduce new storage items that will
become part of the blockchain state. These storage items can be simple
single values, or more complex storage maps.

Example

.. code:: python

   result = portaldot.query('System', 'Account', ['F4xQKRUagnSGjFqafyhajLs94e7Vvzvr8ebwYJceKpr8R7T'])

   print(result.value['nonce']) 
   print(result.value['data']['free'])

**State at a specific block hash**

.. code:: python

   account_info = portaldot.query(
       module='System',
       storage_function='Account',
       params=['F4xQKRUagnSGjFqafyhajLs94e7Vvzvr8ebwYJceKpr8R7T'],
       block_hash='0x176e064454388fd78941a0bace38db424e71db9d5d5ed0272ead7003a02234fa'
   )

   print(account_info['nonce'].value)
   print(account_info['data']['free'].value)

**Type decomposition information**

Some storage functions need parameters and some of those parameter types
can be quite complex to compose.

To retrieve more information how to format those storage function
parameters, the helper function ``get_param_info()`` is available:

.. code:: python

   storage_function = portaldot.get_metadata_storage_function("Tokens", "TotalIssuance")

   print(storage_function.get_param_info())

**Querying multiple storage entries at once**

When a large amount of storage entries is requested, the most efficient
way is to use the ``query_multi()`` function. This will batch all the
requested storage entries in one RPC request.

.. code:: python

   storage_keys = [
       portaldot.create_storage_key(
           "System", "Account", ["F4xQKRUagnSGjFqafyhajLs94e7Vvzvr8ebwYJceKpr8R7T"]
       ),
       portaldot.create_storage_key(
           "System", "Account", ["GSEX8kR4Kz5UZGhvRUCJG93D5hhTAoVZ5tAe6Zne7V42DSi"]
       ),
       portaldot.create_storage_key(
           "Staking", "Bonded", ["GSEX8kR4Kz5UZGhvRUCJG93D5hhTAoVZ5tAe6Zne7V42DSi"]
       )
   ]

   result = portaldot.query_multi(storage_keys)

   for storage_key, value_obj in result:
       print(storage_key, value_obj)

**Query a mapped storage function**

Mapped storage functions can be iterated over all key/value pairs, for
these type of storage functions ``query_map()`` can be used.

The result is a ``QueryMapResult`` object, which is an iterator:

.. code:: python

   # Retrieve the first 199 System.Account entries
   result = portaldot.query_map('System', 'Account', max_results=199)

   for account, account_info in result:
       print(f"Free balance of account '{account.value}': {account_info.value['data']['free']}")

These results are transparently retrieved in batches capped by the
``page_size`` kwarg, currently the maximum ``page_size`` restricted by
the RPC node is 1000

.. code:: python

   # Retrieve all System.Account entries in batches of 200 (automatically appended by `QueryMapResult` iterator)
   result = portaldot.query_map('System', 'Account', page_size=200, max_results=400)

   for account, account_info in result:
       print(f"Free balance of account '{account.value}': {account_info.value['data']['free']}")

Querying a ``DoubleMap`` storage function:

.. code:: python

   era_stakers = portaldot.query_map(
       module='Staking',
       storage_function='ErasStakers',
       params=[2100]
   )

