---
id: mining
title: Mining
sidebar_label: Mining
---

Mining is essentially the process of using your computer to help verify and secure a cryptocurrency network, in our case, it is the Cirquity network. By doing this, you will be rewarded with CIRQ. If you want to learn about cryptocurrencies, mining is a great place to start!

There are currently a few different ways in which you can start mining Cirquity:

## Desktop mining
### XMRig

[XMRig](https://github.com/xmrig/xmrig) uses separate miners for CPU and GPU, you need to download a CPU and GPU miner separately and run two separate instances on your computer.

* ### `Download and install on Windows`

    XMRig has separate miners for CPU and GPU. You can download them from here:
    
    * [XMRig CPU Miner](https://github.com/xmrig/xmrig/releases)
    * [XMRig GPU NVIDIA Miner](https://github.com/xmrig/xmrig-nvidia/releases)
    * [XMRig GPU AMD Miner](https://github.com/xmrig/xmrig-amd/releases)
    
    **Note:** You will need to download and run two separate instances if you want to mine with your GPU and CPU at the same time.

* ### `Download and install on Linux`
    
    You can directly use the pre-built binaries for XMRig CPU. Download the `xmrig-*-xenial-amd64.tar.gz` file [here](https://github.com/xmrig/xmrig/releases).  
    Run the file using `./xmrig`. 
    
    XMRig needs to be compiled for NVIDIA and AMD. Instructions for compiling are linked below(Ubuntu):
    
    * [XMRig GPU NVIDIA Miner](https://github.com/xmrig/xmrig-nvidia/wiki/Ubuntu-Build) 
    * [XMRig GPU AMD Miner](https://github.com/xmrig/xmrig-amd/wiki/Ubuntu-Build) 
    * [XMRig CPU Miner](https://github.com/xmrig/xmrig/wiki/Build) (instructions for multiple platforms)

* ### `Download and install on Mac`

    Needs to be compiled. Instructions [here](https://github.com/xmrig/xmrig/wiki/OS-X-Build).

* ### `XMRig Setup and Configuration`
    
    #### CPU XMRig Configuration
    
    1. Unzip the file and extract the files into a new folder (Make sure your anti-virus doesn't delete the files)
    2. Open the `config.json` file with Notepad
    3. Find and change the following lines:
        1. `"algo: "cn-lite"`
        2. `"url: "[pool address]"`
        3. `"user: "[wallet address]"`
        4. Instead of `[wallet address]`, simply paste your Cirquity wallet's address. Make sure to keep the `"`!
            * If you don't have one yet, you can find out how to create a wallet [here](/guides/wallet)
        5. In place of `[pool address]`, you'll need to choose a pool to mine towards. You can learn more about them [here](/guides/mining#pools). Make sure to keep the `"`s!
        6. Save the file and:
            * start `xmrig.exe` if you're mining with your CPU,
            * `xmrig-amd.exe`. if you're mining with an AMD GPU,
            * or `xmrig-nvidia.exe` if you're mining with a NVIDIA GPU.
    
    **Remember:** if you want to mine with both your CPU and your GPU you must have both programs open at the same time!
    
    That's it! You should be mining away now! :)

### Solo mining

Solo-mining Cirquity means that you, alone, try to find the next block.  
**It is extremely hard, and not recommended** - try our [other guides](/guides/mining) if you want a more steady flow of CIRQ.  
Solo-mining is limited to *only your CPU*.

If you're sure you want to solo mine, let's continue.

* ### `Setup and running`

    Make sure you have  `cirquityd` and `miner`, both can be found in [the latest release](https://latest.cirquity.com).    
    
    *Note*: If they aren't there, you'll have to compile it yourself:
    
    * [Linux](https://github.com/cirquity/cirquity#linux)
    * [OSX](https://github.com/cirquity/cirquity#osxapple-using-clang)
    * [Windows](https://github.com/cirquity/cirquity#windows)
    
    Ensure **`cirquityd`** is running and fully synced.
    
    #### Windows
    Go to your folder that has `miner.exe` in it and start a cmd prompt.  
    
    - This can easily be done by moving to the `cirquityd.exe` directory in Windows Explorer, then typing `cmd` in the search bar and hitting enter.
        
    #### Linux / OSX
    You may be able to right click on your directory and "Open in" Terminal
        
    - When it opens, type:  
        `miner --address cirq... --threads 4 --scan-time 1 --log-level 3`
    
    - Replace `cirq...` with your Cirquity public address.  
        We recommend setting the `--threads` option to half of how many you have. So if you have 12 threads in your CPU, set it to `6`.  
        
        Example:  
        ```bash
        miner --address cirqgEvJZj3bkP7Pwu8hrvhxPojoeVpJSg5sV9CU58oNLJWqJ3usg3kNNxb9ucX8Y5Spjwm1PBLRZ4QGEcn93LAdaWcTU9mQZaG --threads 4 --scan-time 1 --log-level 3
        ```
    
    Congratulations, you are now solo mining Cirquity from your CPU.
    
* ### `Important notes`
    
    * `cirquityd` *must* stay running for the miner to mine Cirquity.  
    * Be patient. Finding a block may happen within the first few hours of mining. It also may take a week. Or it may never happen.  
    * If you accidentally close out `cirquityd` you can restart the miner by hitting Ctrl+C on your keyboard, then re-entering the miner command given above.  
    * You may have to adjust the amount of threads based on your PC's capabilities(half of how many your CPU has is recommended).

## Pools

Unless you want to [solo mine](/guides/mining#solo-mining), which is unfeasible for many people, you will need a pool to mine towards. Make sure to choose the one closest to you!

To view a list of pools, check out [the explorer](https://explorer.cirquity.com/pools.html)

* ### Definition of fees

    Rather simple; the pool operator will take a percentage of the reward of the block found for himself.

    Example:
    
    - the fee is 0.1%
    - the block reward is 30000 CIRQ
    - 30000 x 0.1% = 30

    Therefore, the pool operator will take 30 CIRQ for himself.

    
* ### Definition of different types of methods
    
    These will be found on the pool website; if not specified, it is most likely proportional.
    
    * ### `Proportional (share-based)`
    
        A proportional pool carries no risk to the pool operator as miners are simply paid out when a block is found. No blocks, no payout!
        
        With a proportional pool the risk is all on the miners if it takes longer than expected to find a block then the miners earn less. On the flip side, if the pool is lucky (they will all average out the same eventually) the miners get more.
        
        Example:
        
        - A block is found after 100,000 shares
        - You submitted 1,000 of those shares (you have 1% of the pool's total hash power)
        - There’s 30000 CIRQ per block
        
        Quite simply you will get 1% of the block = 300 CIRQ.
        
        Now if the pool has a bad round (a round is the time taken to find a block) and it takes 200,000 shares to find a block (twice as long) and you have submitted 2,000 shares (as you’ve been mining twice as long), you still only get 1% of the block = 300 CIRQ
        
        This can also work in the miners favor too, as if it takes half the time (50,000 shares) to find a block and you submitted only 500 shares - again 1% - 300 CIRQ.
        
        Basically, you always get a percentage of the block and you win/lose depending on the “luck” of the pool.
        
        The drawbacks to a proportional pool are that there is often a fee, although some pool operators rely on donations only, and you will have to bear the variance of the block times and luck unlike a PPLNS pool.
        
        Also they are susceptible to “pool hoppers” where PPLNS pools are not.
    
    * ### `PPLNS (Pay Per Last *n* Shares)`
    
        PPLNS does not pay out per block found, rather it pays based on the number of shares you last submitted, and helps to dissuade pool hoppers.
        
        How it works:
        
        * You start mining with a PPLNS pool.
        * Rather than paying you out based on the number of shares you submitted since you started mining/the last block was found, it will pay depending on how many shares you submitted in a period of time, called the window, which is an estimate of the time in which the pool in question finds a block.
        * So, after you start mining, it will take a few hours for you to earn your normal earnings - and since the effect of pool hoppers is lessened, you may make comparatively more than other methods.
        
        Basically, you get paid based on
        
        - the number of shares you submitted (how good what you're mining with is)
        - and how long you have been mining.

## Have questions or need help?

Check out our [Discord](http://chat.cirquity.com) to get in touch.
