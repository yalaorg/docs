# How $YU Maintains Stability

$YU is a stablecoin designed to provide a reliable medium of exchange and store of value within the DeFi market and the Bitcoin ecosystem. Anchored in Bitcoin as its primary collateral, $YU aims to maintain a stable value with a soft-peg reference to the US dollar.\
\
$YU maintains stability through over-collateralization, stability fees, liquidation mechanisms, and incentivized operators. The system continually monitors collateral and valuation levels and adjusts risk parameters to manage fluctuations and maintain the peg.&#x20;

The combination of stabilization mechanisms from smart contracts, risk parameter adjustments, and actions by incentivized market actors, such as Keepers (bots or external actors that maintain system stability by liquidating under-collateralized vaults and stabilizing $YU's price through arbitrage), helps balance $YU's supply and demand and its soft peg to the dollar.&#x20;

### Mechanisms for stability

$YU maintains its soft peg to the US dollar through a set of stabilization mechanisms involving several key components:

#### Over-collateralization

$YU is backed by Bitcoin, the primary collateral in a smart contracts system. This over-collateralization ensures that the value of the collateral in the system always exceeds the value of the $YU issued, providing a global buffer against underlying collateral pricing fluctuations. The protocol regulates the required level of over-collateralization by assigning collateralization ratios and debt ceilings for each collateral type via governance. &#x20;

* **Mechanism:** Users lock up more collateral than the value of the $YU debt they generate. For example, given a collateral ratio of 110%, if a user locks up $110 worth of BTC, they can generate up to $100 in $YU. This collateral buffer helps absorb price fluctuations in collateral assets.
* **Example:** If BTC's value drops significantly, the collateralization ratio is maintained by liquidating the collateral to cover the $YU debt. This helps keep $YU's value stable even if the collateral value changes.

**Stability Fees**

A stability fee incentivizes users to adjust their vault positions. Users must pay a stability fee to generate $YU debt, calculated as a percentage of the debt issued. This fee helps manage the supply of $YU by influencing users' decisions on whether to generate or repay $YU.

* **Mechanism:** Stability fees are charged as a percentage of the $YU debt for each vault. This fee manages the overall supply and demand for $YU. When $YU is below the peg, higher fees can discourage the creation of new $YU or encourage repayment of existing $YU, helping to push the price of $YU upwards by reducing its supply. Alternatively, low fees encourage users to mint $YU to increase the supply of $YU in the market in case $YU is above the peg.&#x20;
* **Example:** If the stability fee is increased, it becomes more costly to hold $YU debt, which may encourage users to repay their debt and reduce the supply of $YU, helping stabilize the price towards the peg.

**Liquidation System**

The protocol includes automated liquidation mechanisms and a set of incentivized actors (Keepers) to manage collateral levels. Suppose the collateral value falls below a predefined threshold for a given collateral type. In that case, the system triggers the liquidation of assets via collateral auctions to restore the required minimum collateralization ratio. This process helps to maintain the stability of $YU by ensuring that the assets backing $YU remain sufficient.

* **Mechanism:** When the value of defined collateral falls below a certain threshold (the liquidation ratio), the collateral is sold through an auction to repay the $YU debt. This prevents the system from becoming under-collateralized and maintains the value of $YU.
* **Example:** If a user's collateral falls below the required ratio due to a drop in BTC’s price, the user’s collateral is liquidated at a collateral auction to cover the $YU debt, preventing any shortfall and maintaining the stability of the $YU peg.

**Governance Mechanisms**

A decentralized governance model allows stakeholders to vote on protocol parameters, including stability fees, collateral ratios, and collateral types, ensuring the system can adapt to changing market conditions.

* **Mechanism:** Yala governance adjusts the system's parameters and the types of accepted collateral to manage risks and maintain stability. This includes adding new collateral types with suitable risk profiles or modifying existing parameters.
* **Example:** If a particular collateral type shows increased financial risks, Yala protocol governance may remove it from the system or adjust its parameters to mitigate the risk and maintain stability.

Other mechanisms, such as the Yala Savings Rate (YSR) and stability modules, can also contribute to the supply and demand balance of the $YU stablecoin. By activating the YSR, the system can “nudge” $YU holders to reduce the availability of $YU in the market, which is locked in the YSR contract.&#x20;

### Role of collateral

Over-collateralization is crucial to the stability of $YU. The protocol requires a higher value of Bitcoin as collateral than the value of $YU issued. This approach serves multiple purposes:

1. **Security Buffer:** The protocol creates a reserve cushion by requiring that the value of Bitcoin collateral exceeds the value of $YU issued. This buffer absorbs price fluctuations and helps maintain the stablecoin’s value.
2. **Risk Management:** Over-collateralization mitigates the risk of insolvency. Even if Bitcoin’s value decreases, the excess collateral ensures that $YU remains fully backed, reducing the likelihood of a destabilizing event.
3. **Incentive Alignment:** By requiring a higher collateral value, the protocol aligns the interests of vault participants with its price stability objective. Users are incentivized to maintain adequate collateral levels to avoid liquidation while the protocol retains the value of $YU. Both support the long-term stability of $YU.
