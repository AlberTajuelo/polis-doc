![Polis](https://github.com/polispay/polis-doc/raw/master/resources/polis.png "Polis")

# How to create a budget proposal (testnet)

## Before you start
Before you start working with governance proposal on testnet, you need to make sure you are running the polisd daemon on testnet. To do so you need to download the wallet as normal (make sure you are running v1.2.2).

## Starting Daemon on testnet

To start the daemon on test network you need to change your polis.conf parameters adding the line ```testnet=1```
You can find the polis.conf on the following paths:

* Windows: ```%APPDATA%\polisCore.```
* Linux: ```~/.poliscore.```
* macOS: ```~/Library/Application Support/polisCore```

## Starting proposal

Now that you have your daemon working on testnet you need to make sure your blockchain is working on the same block than testnet.polispay.org.

To start a proposal you need to go to proposal.polispay.org. Make sure you are using the testnet tab.

Once you fill the information, you need to put an address that will receive the tpolis amount on the testnet, to do so you must generate an address before.

The webpage is going to show the process on how to submit the proposal to the network. To do so, you need 5 tpolis. To get them you can start mining on the testnet, is very low diff so you will get the testnet polis very fast.

## Voting on governance

To vote for your own proposal you must have a masternode enabled on the testnet. To do it, you need to follow the same process as the mainnet but using daemons connected to the testnet.

Once the daemon the masternode is enabled you must run the command from the debug console:

```polis-cli gobject vote-many GOBJECT-HASH funding yes```

If the governance object gets more than the 10% of MN votes as funding, you will receive the payment on the next superblock.  
