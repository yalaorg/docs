# Liquidation

Yala Protocol's liquidation mechanism ensures the stability and efficiency of the system by managing under-collateralized vaults through automated processes inspired by LiquityV2. The system employs Stability Pools as its primary mechanism to absorb liquidated debt and collateral, complemented by additional safeguards to maintain stability during market volatility. Below is an overview of the liquidation process for the YBTC vault.

#### **1. Liquidation Trigger: Monitoring Collateralization**

The protocol continuously monitors vaults to ensure their **Collateralization Ratio (CR)** remains above the **Minimal Collateral Ratio (MCR)** of **110%**. A vault is flagged for liquidation if its CR drops below this threshold. This ensures that every vault remains adequately collateralized to cover its debt and maintain system solvency.

**Key Parameters:**

* **Minimal Collateral Ratio (MCR):** 110% - Triggers liquidation for individual vaults.
* **Critical Collateral Ratio (CCR):** 150% - If the system's total collateral ratio (TCR) falls below this level, users cannot perform actions that further reduce the TCR.
* **Shutdown Collateral Ratio (SCR):** 110% - If the TCR of all vaults falls below SCR, the system will initiate a global shutdown to protect user assets.

#### **2. Stability Pools: Primary Liquidation Mechanism**

Yala utilizes **Stability Pools** as the primary liquidation mechanism:

* **Stability Pool Contributions:** Users deposit $YU into the Stability Pool, which is used to burn the liquidated debt and absorb the collateral. Stability Pool participants receive the liquidated YBTC as a reward for their contributions.

This automated process ensures quick and efficient liquidation, reducing risks to the protocol and minimizing exposure during volatile conditions.

#### **3. Gas Compensation for Liquidation Initiators**

The protocol incentivizes liquidation initiators by offering **gas compensation** to cover the costs of initiating the process. This compensation is calculated as:\
**200 $YU + min(0.5% of YBTC, 0.05 YBTC)**.

This ensures that liquidations are fair and accessible while incentivizing participation from the community.

#### **4. Fallback Mechanisms for Liquidations**

If the Stability Pool is depleted and cannot cover the entire debt, Yala implements fallback mechanisms to handle the remaining liquidation:

**Redistribution:** The remaining debt and collateral are redistributed proportionally to all borrowers in the same collateral market, spreading the risk across users.

#### **5. Liquidation Penalty**

Liquidated vaults incur an **8% penalty** on their debt, which is absorbed by the Stability Pool. This penalty incentivizes vault owners to maintain healthy collateralization levels and compensates Stability Pool participants for taking on additional risk.

#### **6. Post-Liquidation Outcomes**

After a vault is liquidated:

* The remaining collateral (after covering debt and penalties) is returned to the vault owner, ensuring they retain any surplus beyond the liquidation requirements.
* The liquidated debt is removed from the system, maintaining the stability of the protocol.

**7. Preventive Measures and Risk Management**

To minimize the frequency of liquidations and protect the protocol and its users, Yala employs several preventive measures:

* **Collateralization Alerts:** Users are notified when their vault’s collateralization ratio approaches the liquidation threshold. This allows them to add more collateral or repay some debt to avoid liquidation.
* **User Dashboard and Tools:** A user-friendly dashboard displays real-time data on collateral prices, debt ratios, and liquidation thresholds, helping users manage their positions actively.

#### **8. Key Parameters for YBTC Vaults (Testnet)**

* **Interest Rate (Stability Fee):** 4% annually.
* **Debt Ceiling:** 1,000,000,000 $YU.
* **Minimum Debt (Dust Floor):** 2,000 $YU.
* **Liquidation Penalty:** 8%.
* **Gas Compensation:** 200 $YU + min(0.5% of YBTC, 0.05 YBTC).

### Conclusion <a href="#conclusion" id="conclusion"></a>

Yala Protocol's liquidation process is designed to prioritize system stability, efficiency, and fairness. By utilizing Stability Pools as the primary mechanism and incorporating fallback options like JIT liquidations and redistribution. With robust safeguards, transparent operations, and user-focused tools, the protocol remains solvent while providing transparent and effective risk management for all participants.
