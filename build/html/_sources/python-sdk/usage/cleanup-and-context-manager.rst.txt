Cleanup and context manager
===========================

.. toctree::
   :maxdepth: 4

At the end of the lifecycle of a ``SubstrateInterface`` instance,
calling the ``close()`` method will do all the necessary cleanup, like
closing the websocket connection.

When using the context manager this will be done automatically:

.. code:: python

   with SubstrateInterface(url="wss://rpc.polkadot.io") as portaldot:
       events = portaldot.query("System", "Events")
