# IoP Blockchain Beta
## Release Notes

## version 1.0.0
Initial Miner Whitelist implementation. 

* It supports adding and removing miners into the white list.
* Embedded miner activated.
* Premined value on block 1 of 2.100.000 tokens.
* Coinbase blocks limited to 1 IoP per block

## version 1.1.0
Small fixes to the whitelist implementation which include: 

* New parameters for admins public keys into chainparams divided by network.
* correct retrieval of admin miner from whitelist db.

## version 1.2
Security improvements which include:

* removal of minerPKey parameter as  startup command on IoP.conf file
* incorporation of new parameter called minerWhiteListAddress which reads the base 58 address to avoid having the private key visible.


## version 2.0
New functionality called Miner Cap introduced on the client.

* The blockchain now supports to new types of transaction:
	* **enable_cap:n**: used to enable the miner cap control and set the n factor used to calculate the minerCap.
	* **disable_cap**: used to disable the miner cap control.

The miner Cap control is used to limit the amount of blocks each miner can submit to the network.

* New RPC command called **dumpMinerStats** use to generate a JSON output with the amount of blocks each miner has mined since the white list control has been activated.	


## version 2.0.2

Small improvements:

* fixed compilation warning for enum not initilized in main.cpp
* added new information to output of dumpminerstats: currentWhitelisted miners.
* removed tr1 prefixes from code to avoid compilation errors in OS X.

Small fixes:

* corrected seed nodes IPs for both testnet and mainnet to avoid errors on debug.log file.
* removed comments that where printing out debug information to console related to connections to peers.