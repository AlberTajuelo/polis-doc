![Polis](https://github.com/polispay/polis-doc/raw/master/resources/polis.png "Polis")

# Voting Budget Proposals

If you want to vote a Budget Proposal, you must own a masternode.

## Vote Calculation

The actual calculation is (YES votes - NO votes) > (Total Number of Masternodes / 10).

If there are 1000 masternodes, your budget proposal should need at least 100 YES votes without a NO vote.

## List Budget Proposals

### Using Polis Ninja Website

You can check using [Polis Ninja website](https://polis-ninja.org/governance.html).

### Using Polis Core Wallet

Open your Polis Core wallet on your desktop and now click on "Tools" tab and press on "Debug console".

```
gobject list
```

## Voting options

This are the following voting options:
* Yes
* No
* Abstain

## Voting using Polis Core Wallet

To vote with all masternodes you have at once:

```
gobject vote-many <proposal_hash> funding <yes/no/abstain>
```

Example:
```
gobject vote-many 68f62bc84f7fef0ca3f5c6fe71b48a6878340c573ca29a6554351c63a30d8538 funding yes
gobject vote-many 68f62bc84f7fef0ca3f5c6fe71b48a6878340c573ca29a6554351c63a30d8538 funding no
gobject vote-many 68f62bc84f7fef0ca3f5c6fe71b48a6878340c573ca29a6554351c63a30d8538 funding abstain
```
