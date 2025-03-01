# Tech

### 1. What is your innovation?

Yala’s innovation lies in a) technology and b) yield, ensuring its long-term industry leadership.

From the technology perspective, Yala pioneers:

* **Unified Liquidity Layer**\
  Yala’s ultimate goal is to create a revolutionary, chain-agnostic framework that addresses liquidity fragmentation and enhances user capital efficiency.
* **MetaVault**\
  MetaVault is an advanced version of a simple vault designed to meet diverse risk preferences and offer flexible asset management. It establishes a robust omnichannel vault standard.
* **BTC Self-Custody (for large clients)**\
  Users’ Bitcoin is locked in self-custody accounts using a trustless, multi-signature script (P2SH) with a time-lock feature. This ensures asset security and user control while generating BTC LST yields and $YU yields.

From the yield perspective, Yala adopts a novel approach to multi-chain yield generation, allowing BTC holders to earn yields across multiple chains while maintaining Bitcoin-native security.&#x20;

* **BTC & LSTs**\
  Yala accepts both native BTC and Liquid Staking Tokens to optimize returns.
* $**YU on DeFi & RWA**\
  Yala aggregates yield opportunities across DeFi platforms and RWAs via its stablecoin $YU.
* **Lite Mode**\
  Yala designs an on-chain portfolio management system curating investment pools to optimize yield through strategic combinations.



### 2. How are the assets stored and how many confirmation blocks would it have?

* **Pro-Mode:** Native BTC will be stored at Yala, while private keys will be managed by Cubist, a third-party security expert specializing in key management.
* **Lite mode:** Native BTC are sent to Yala MetaVault. The security here depends on the Vault’s permission control, custody method, and fund strategy.
* **Self-Custody Mode:** Native BTC will remain locked in the user’s own custodial account.

Yala implements a 6-block confirmations for more safety as more blocks increase transaction security. After 6 blocks, transactions are typically immutable and tamper-proof. Other protocols, such as Babylon and Lombard, also adopt the 6-block standard.

### 3. Where is the Yala Vault for accessing Bitcoin LSTs stored, and how are they secured?

There are 3 scenarios:

1. **On ETH or ETH/BTC-related Layer 2s,** users directly use Bitcoin LSTs as collateral using Yala Pro mode. In this case, the security within Yala depends solely on the Yala core module (fork from [LiquityV2](https://www.liquity.org/))
2. **On BTC:** Users utilize MetaVault's Lite mode to deposit native BTC. The fund manager (Vault operator) can convert the BTC into Bitcoin LSTs and use them as collateral within their operational permissions. The security here depends on the Vault’s permission control, custody method, and fund strategy.
3. **On the chosen destination chain:** Large holders self-custody and use a P2WSH script to ensure their native BTC remains controlled while generating LSTs on the destination chain. Assuming the script code is secure, the underlying BTC’s security is theoretically on par with Bitcoin’s mainnet (and these BTC will not face liquidation risk)

### 4. Can you explain how you do better than a bridge protocol?

For Bridge and MetaMint, Please review the following flow:

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeSpFXyxyJoz6XPy6e0VIhJXcls1VQsIcBd4dfZ80oNcnKeoiKgFpSy-Gr5R5Vz76PgvQKkXCE88OJno4tIUtXY6bVqD4ZAvIuIBiDXaEndjHyC3ApOs7ECsGuF55NVPRHkLvx1rw?key=px95Af-krYL27PiTLOgOJuEX" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXecuhxRE4uaQ7c8DJFkaT6xAbNNdC_5m1nfO6kEAzn-nIAwWH_LTpVFVJIoEOnHHEa0tcQCGEDpfxqy2lgzScDIPkT_QTGb60mwYGWQDQAkK2Fq6IQ14FSVIR0j6BrkNrTcgGwVbg?key=px95Af-krYL27PiTLOgOJuEX" alt=""><figcaption></figcaption></figure>

Compared to conventional bridges that lock the asset in the smart contract to create a wrapped version on the destination chain, Yala allows customers to keep the BTC in their wallet or on the BTC mainnet and mint a certificate (YBTC) of this asset that is used in the smart contract to mint the stablecoin $YU.

The notaries manage the Yala bridge and are responsible for signing messages for BTC bridge in and out transactions. Yala requires 11 notaries, at least 9 of whom are randomly selected, to validate transactions decentralized. Notaries include institutions, investors, node operators, clients, custodians, and CEXs.

### 5. What backend mechanism enables the minting of $YU to multiple chains?

There are two ways to mint $YU on multiple chains.&#x20;

1. The Notary Bridge supports generating YBTC on the target chain through MetaMint while deploying Yala CDP-related contracts on the target chain. Users can mint $YU on the target chain using YBTC or other collateral.&#x20;
2. $YU will support native mint/burn cross-chain functionality, similar to the USDC CCTP implementation.

\
