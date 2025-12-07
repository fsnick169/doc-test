SDK Extension
==================

.. toctree::
    :maxdepth: 4

This extensions is meant as a fallback option that uses only existing Portaldot RPC methods. 
However, it is important to note that this fallback implementation is significantly inefficient, 
and it is encouraged to utilize third-party search indices where possible for optimal search performance.

---------------------


**Initialization**

.. code:: python

    from substrateinterface import SubstrateNodeExtension

    portaldot = SubstrateInterface(
      url="wss://mainnet.portaldot.io",
      ss58_format=42,
      type_registry_preset='default'
    )

    # Provide maximum block range (bigger range descreases performance) 
    portaldot.register_extension(SubstrateNodeExtension(max_block_range=100))


**Implemented extension calls**

.. code:: python

    # filter_events
    # Returns all `Balances.Transfer` events in block range #3 until #6
    events = portaldot.extensions.filter_events(pallet_name="Balances", event_name="Transfer",  block_start=3, block_end=6)



.. code:: python

    # filter_extrinsics
    # All TransferKeepAlive extrinsics in block range #3 until #6
    extrinsics = portaldot.extensions.filter_extrinsics(pallet_name="Timestamp", call_name="transfer_keep_alive", block_start=3, block_end=6)


**Search block number**

.. code:: python
    
    # Search for block number corresponding a specific datetime
    block_datetime = datetime(2020, 7, 12, 0, 0, 0)
    
    block_number = portaldot.extensions.search_block_number(block_datetime=block_datetime)


**Get block timestamp**

.. code:: python

    # Get timestamp for specific block number
    block_timestamp = portaldot.extensions.get_block_timestamp(block_number)

