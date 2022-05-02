.. quickstart:

Quickstart
==========

In this quickstart quide, you will install the Python Terra SDK,
connect to a Terra node, and query the latest block height.

.. note:: All code starting with a ``$`` is meant to run on your terminal.
    All code starting with a ``>>>`` is meant to run in a python interpreter,
    such as `ipython <https://pypi.org/project/ipython/>`_.

Installation
------------

Install the Terra SDK using ``pip``:

.. code-block:: shell

   $ pip install terra-sdk 


.. note:: If you run into problems during installation, you might have a
    broken environment. See the troubleshooting guide to :ref:`setting up a
    clean environment <setup_environment>`.

.. note:: It is recommended that you install the Terra SDK in a :ref:`virtualenv <setup_environment>`.

Using Terra SDK
---------------

In order to interact with the Terra blockchain, you'll need to connect to a Terra node.
To connect to a node, set up the LCDClient:


.. code-block:: python

    from terra_sdk.client.lcd import LCDClient

    terra = LCDClient(chain_id="columbus-5", url="https://lcd.terra.dev")
    print(terra.tendermint.node_info())


Getting Blockchain Info
-----------------------

It's time to start using Terra SDK! Once properly configured, the ``LCDClient`` instance will allow you
to interact with the Terra blockchain. To get the latest block height, run the following code:

.. code-block:: python

    >>> terra.tendermint.block_info()['block']['header']['height']
    '1687543'

In addition to reading block data, you can also sign and send transactions, deploy and interact with smart contracts,
and interact with the Terra blockchain using the Terra SDK.
