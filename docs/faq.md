---
id: faq
title: Frequently Asked Questions
---

## Daemon and Wallet
#
### How can I re-sync the blockchain?

Close any `Cirquity` related software, then go to `%APPDATA%`, and delete the `Cirquity` folder.  
Reopen `cirquityd` / `the GUI wallet` and let it re-sync.

Alternatively, check [this guide](/guides/wallet#using-checkpoints) for instructions on how to use checkpoints for a quicker sync, or try a [remote node](/guides/wallet#using-remote-nodes)
#
### I'm getting a "corrupted blockchain" error like this?

```bash
2018-May-07 15:52:19.877323 INFO    Initializing core
2018-May-07 15:52:19.908530 INFO    Importing blocks from blockchain storage
2018-May-07 15:52:19.908530 ERROR   Corrupted blockchain. Block with index 428973 and hash aafa7fd33d476535188bdd9e86ba51bb5e058be8e52367b78e9c0c03e74299c5 has previous block hash 2c0cf6c07612b9e1ea19c6922a56746b83cb42c7b11edfc4b185572225bb0f20, but parent has hash 26189359b64d4bb357a04b102a42a01d2771a3f3d80db3ca1b7395a2aeaede4a. Resynchronize your daemon please.
2018-May-07 15:52:19.924135 INFO    Closing DB.
```

Re-sync your daemon from [scratch](/faq#how-can-i-re-sync-the-blockchain)
#
### I'm getting a "Genesis block hash was not found" error like this?

```bash
2020-Mar-26 13:41:31.655981 ERROR   Failed to get wallet sync data: Genesis block hash was not found.
```

Re-sync your wallet from [scratch](/faq#how-can-i-re-sync-the-blockchain)
##### Using Desktop GUI
* Backup your wallet then close your GUI Wallet
* Delete the `.wallet` file
* Then open the GUI Wallet and re-import your wallet. It should start counting up the blocks and printing out your transactions as it gets to them.
#
### I've opened the wallet, and I'm getting lots of messages like "Your cirquityd isn't fully synced yet!"

```bash
Until you are fully synced, you won’t be able to send transactions, and your balance may be missing or incorrect!
```

Your daemon hasn't finished syncing yet. Keep cirquity-wallet open, and wait until you are `0` days behind the current block, and for the daemon to print out a green message saying `Successfully synchronized with the Cirquity Network`.  
You can also type status in the daemon and press enter to see the current height it's at.

