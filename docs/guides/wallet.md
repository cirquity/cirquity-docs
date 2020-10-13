---
id: wallet
title: Wallet
sidebar_label: Wallet
---

There are multiple different types of wallets you can choose to use for Cirquity, Paper wallets, CLI wallets, GUI wallets and Web Wallets.

We recommend making a Paper wallet so that you can start receiving funds, and later import them into a GUI or CLI wallet.


## Paper Wallet

The main purpose of a paper wallet is to quickly create a wallet to start receiving funds.

You will not be able to spend or send your funds to other people until you set up a CLI, GUI or Web Wallet.

Go to [this link](https://cirqwallet.com/paper) and follow these steps.

* ### `Generating the Wallet`
    
    * Mash your keyboard and start entering a bunch of random letters, numbers and signs in the field. Make sure you toggle on Caps Lock repeatedly! (Don't go too crazy - otherwise you might end up shutting down your PC!)
    * After you're done mashing your keyboard, press `Generate Wallet`
    * The letters and numbers in the green box, starting with `cirq`, is your public address. You can share it freely.
    * Save the Seed Phrase, the 25 words in the red box, safely.  
        **DO NOT SHARE IT WITH ANYONE**.  
        Anyone who has access to this can access your funds and has complete control over your wallet.
    * Save the Spend Key and the View Key, the two very long strings of (seemingly) random letters and numbers, safely.  
        **DO NOT SHARE IT WITH ANYONE**.  
        Anyone who has access to this can access your funds and has complete control over your wallet.
    * Click `Print Your Wallet Details` if you what to download a PDF file with all the wallet details
    
## Cirquity-Wallet (CLI Wallet)

The CLI Wallet, called cirquity-wallet, is a multi-platform program (Win/Linux/Mac) that requires you to enter commands for it to work and you cannot use your mouse. However, it is currently the most stable and gets the newest updates first.

* ### `Using cirquity-wallet`

    Binary distributions can be found here.  
    Select the appropriate file for the target platform (Windows, Mac, Linux).  
    Binaries are provided in .zip format, while source code is provided in .zip and .tar.gz format.
    
    #### Installing
    
    1. Windows  
        Extract the .zip file (`cirquity-...-windows.zip`).
        Right click on the .zip file and select `Extract files on folder`
    2. Mac  
        Extract the .zip file
        ```
        unzip cirquity-...-mac.zip
       ```
    3. Linux  
        Extract the .zip file
        ```
        unzip cirquity-...-linux.zip
       ```
    
    #### Synchronizing the Blockchain
    
    Running **cirquityd** will start the _cirquityd_ network daemon, which will connect to the network and begin downloading and verifying the Cirquity blockchain.  
    Because the blockchain is constantly growing, the file size always increases, and cirquityd must verify every block, which is both CPU and disk intensive. An SSD with at least this much free disk space is recommended, unless you plan to use remote nodes.
    
    #### Using Checkpoints
    
    In **versions 0.3.1+** you can sync a fresh chain from 0 much quicker by loading "checkpoints" with your daemon.

