Munin-Node plugin to monitor Fulcrum and Bitcoin
------------------------------------

This plugin was heavily based on the wonderful munin plugin by 
Samuel Smith @ https://github.com/shsmith.

These Munin-Node plugins gather data from your running instance of 
Fulcrum server and/or Bitcoin daemon.

Fulcrum server:
    https://github.com/cculianu/Fulcrum
    
Bitcoin daemon:
    https://github.com/bitcoin/bitcoin


Getting Started
---------------

Install munin and apache2.  For Ubuntu systems the commands are::

    sudo apt-get update 
    sudo apt-get install munin apache2

The fulcrum_bw plugin uses nethogs. To install it::

    sudo apt-get install nethogs

Once you have munin up and running, add the following files::

 /etc/munin/plugins/
    bitcoin_blocks
    bitcoin_bw  
    bitcoin_conn
    bitcoin_diff
    bitcoin_du
    bitcoin_fee
    bitcoin_mempool
    bitcoin_mp
    bitcoin_mp2
    bitcoin_peer_versions
    bitcoin_ticker
    bitcoin_ticker_bch
    bitcoin_ticker_bchsv
    bitcoin_tx
    bitcoin_vm
    fulcrum_bw
    fulcrum_caches
    fulcrum_client_protocol
    fulcrum_client_versions
    fulcrum_connrate
    fulcrum_err
    fulcrum_io
    fulcrum_lsof
    fulcrum_mem
    fulcrum_peers
    fulcrum_peer_versions
    fulcrum_reqcounts
    fulcrum_ses
    fulcrum_sub
    fulcrum_tx
    fulcrum_users

These plugins require configuration. 
The configurations are in the following files added to your plugin-conf.d folder.::

 /etc/munin/plugin-conf.d/
    bitcoin
    fulcrum

You will need to edit /etc/munin/plugin-conf.d/bitcoin. 
*******************************************************

- Adjust the ``BITCOIN_DATADIR`` environment to specify where to find your bitcoin data directory.
- Adjust the ``BITCOIN_CLI`` environment to specify where to find bitcoin-cli.

You will need to edit /etc/munin/plugin-conf.d/fulcrum.
*********************************************************

- Adjust the ``FULCRUM_RPC`` environment to specify where to find FulcrumAdmin.

You will need to make the munin plugins executable.
***************************************************

The munin plugins must be marked as executable.
You can do so using this command::

    sudo chmod +x /etc/munin/plugins/*

After configuring the plugins, restart the munin-node service.

Versions
--------

These plugins are working with the following software versions::

 Munin-Node:         2.0.69
 Fulcrum:            1.6.0




