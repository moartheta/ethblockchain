## GFY Net!

#### Configuration

 - Name: gfynet
 - Blocktime: 15sec
 - Chain ID: 888
 - Acct Password: moartheta
 - Ports: Nd1: 30304 Nd2: 30305
 
![networkjson](Screenshots/thetanetconfiguration.PNG)

#### Addresses 

- nd1 Address - 0x931Ea2d7d685Ef86fdE635c0961c9f6886d6fFC5
- nd2 Address - 0xbd5809c569bBC3B0FAB66755a9e6fAc37059F8CF
- enode://8764734ffd78175cf210efd02bc8d23b3820dd40ff2bd866adb2bb04152dbf51ce49ce8c8f19fad61c6021737da3117aaaa8c17a78a3a4af70942f244c3354e7@127.0.0.1:30303

#### Instructions to Run

1) Start Mining nd2: 

```
$ ./geth --datadir nd2 --mine --minerthreads 1 --unlock '0xbd5809c569bBC3B0FAB66755a9e6fAc37059F8CF'
```

Enter password 'moartheta' when prompted

2) Config nd1 to talk to nd2:

```
$ ./geth --datadir nd1 --port 30304 --rpc --bootnodes "enode://8764734ffd78175cf210efd02bc8d23b3820dd40ff2bd866adb2bb04152dbf51ce49ce8c8f19fad61c6021737da3117aaaa8c17a78a3a4af70942f244c3354e7@127.0.0.1:30303" --ipcdisable
```
 *NOTE: You have to unlock nd1 with --unlock '0x931Ea2d7d685Ef86fdE635c0961c9f6886d6fFC5' before this step.  Enter password 'moartheta' when prompted.*
 
 #### Explaining .geth flags
 
 - --mine : Tells the code to mine new blocks
 - --minerthreads : Tells geth how many CPU threads to use during mining (since been deprecated)
 - --rpc : Lets the first node talk to the second node
 - --port : Sets the port to use
 - --bootnodes : Passes the network info needed to find other nodes in the blockchain
 - --ipcdisable : On Windows machines, generates new IPC/Unix sockets because Windows doesn't allow for having multiple sockets running from geth at the same time
 
### Sending a Transaction

1) Open up MyCryptoWallet

2) Create a new Custom Node with the following parameters:

![customnode](Screenshots/gfycustomnode.png)

3) Once connected to your custom node, click "View/Send" and then click "Keystore File" and load the nd1 keystore file from the nd1 folder: [nd1 Keystore File](nd1/keystore/UTC--2021-02-13T19-44-17.296094000Z--931ea2d7d685ef86fde635c0961c9f6886d6ffc5) and enter password 'moartheta'

4) Copy the wallet address from the right hand side into the "To Address" and send yourself from ETH.

5) It should take about 15 seconds for your transaction to mine.  Refresh the "Check TX" button to confirm your transaction was successful.  If it was, you should get a message that looks like this:

![successtx](Screenshots/TransactionSuccessful.PNG)





    