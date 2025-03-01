# How It Works

Yala Bridge is designed to make both minting YU and redeeming your BTC as straightforward and secure as possible.

#### **Minting YU** <a href="#minting-yu" id="minting-yu"></a>

1. **Transfer BTC to Yala’s Bitcoin Receiver Address**:

* To initiate the transfer, send your BTC to a special Bitcoin address provided by Yala. This address is designed to handle cross-chain transactions seamlessly. When sending BTC, you'll include two important pieces of information in the transaction's OP\_RETURN field:
* The destination blockchain (e.g., Ethereum).
* The receiver's address on that blockchain.

2. **Transaction Monitoring and Confirmation**:

* After you send the BTC, Yala Bridge monitors the Bitcoin network for your transaction. Once your transaction is detected, Yala waits for six block confirmations to ensure security.

3. **Mint YU on the Destination Chain**:

* Once confirmed, Yala Bridge mints YU on the destination chain. Based on the current market rate, the YU you receive can be up to 75% of the value of the BTC you sent.

4. **Receive YU and Start Using It**:

* Within approximately one hour, your YU will be sent to your address on the destination chain. You can then use YU across various DeFi platforms, providing a stable asset backed by your BTC.

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>



#### **Withdrawing BTC** <a href="#withdrawing-btc" id="withdrawing-btc"></a>

1. **Burn $YU on the Destination Chain**:

* To withdraw your BTC, you must create a burn transaction on the destination blockchain. In this transaction, you'll specify how much of the token you want to burn and include the Bitcoin address where you want the BTC to be sent.

2. **Transaction Monitoring and Confirmation**:

* Yala Bridge monitors the destination chain for your burn transaction. Once the transaction is detected, Yala waits for 12 confirmations to ensure it is final and secure.

3. **Release BTC to Your Bitcoin Address**:

* After the burn transaction is confirmed, Yala Bridge releases the amount of BTC from its reserves and sends it to your specified Bitcoin address. This process typically takes about one hour.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>
