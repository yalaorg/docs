# Risk Management

Each asset within the Yala protocol is associated with specific risk parameters that influence how it can be deposited and minted. These parameters ensure sufficient margins and incentives are maintained to keep positions collateralized, even in adverse market conditions. For the initial release phase, Yala supports Bitcoin as the collateral asset.&#x20;

Yala’s risk management strategy is built around the collateralization ratio, a crucial measure of the security of your deposited Bitcoin relative to the $YU stablecoins you mint. A higher collateralization ratio indicates a more secure vault, reducing liquidation risk. However, your vault will be at liquidation risk if your collateralization ratio falls to the minimum required threshold (Min. Collateral Ratio). Please refer to the risk parameters section for a deeper understanding of these parameters.

## Impact of Collateralization Ratio Changes

The collateralization ratio is not static; it fluctuates with the value of your deposited Bitcoin. When the value of your Bitcoin increases, your collateralization ratio improves, strengthening the security of your vault and lowering the risk of liquidation. On the other hand, if the value of your collateral decreases relative to the amount of $YU minted, the collateralization ratio will drop, heightening the risk of liquidation.

What is Liquidation, and How Does it Occur? Liquidation occurs when a vault’s collateralization ratio falls below the Min. Collateral Ratio due to a decrease in the value of the collateral (Bitcoin). In such cases, liquidators repay the minter’s $YU debt and any accrued stability fees. The corresponding value and a liquidation fee are then deducted from the collateral. After this process, any remaining collateral is returned to the user.

Preventing Liquidation To prevent liquidation, users can either repay their $YU debt or deposit additional Bitcoin to increase their collateralization ratio above the minimum threshold.

## Post-Liquidation Actions

What Happens After Liquidation? After liquidation, the Yala protocol triggers an auction process for liquidators. The protocol sells the liquidated collateral through an internal market-based auction system known as a Collateral Auction. External participants, known as Keepers, bid in these auctions, aiming to acquire collateral at attractive prices.

The Collateral Auction proceeds cover the vault’s outstanding obligations, including the Liquidation Penalty fee set by Yala’s governance. If any collateral remains after the auction, it is returned to the user’s vault.

\


