# $YU Stablecoin Design

$YU is an over-collateralized stablecoin primarily backed by Bitcoin, designed to maintain a stable value relative to the US dollar.&#x20;

### Core Mechanics

The $YU stablecoin operates through a sophisticated vault-based system known as "Troves." Each Trove represents a collateralized debt position where users deposit Bitcoin as collateral and mint $YU against this value. The protocol's smart contract architecture manages these positions through specialized components: TroveManager handles vault operations and liquidations, BorrowerOperations provides the user interface for creating and adjusting positions, and DebtToken implements the actual $YU token with cross-chain compatibility via LayerZero. This system is designed with security as the primary consideration, leveraging Bitcoin's robust security model while enabling the flexibility of a modern stablecoin.&#x20;

### Overcollateralization Model

$YU implements a dynamic over-collateralization system with multiple thresholds to ensure stability. The protocol maintains three key collateralization parameters: the Minimum Collateralization Ratio (MCR) defines the lowest acceptable collateral-to-debt ratio for individual positions; the Critical Collateralization Ratio (CCR) establishes a target for system-wide collateralization; and the Shutdown Collateralization Ratio (SCR) sets the threshold below which emergency measures may be triggered. As implemented in the TroveManager contract, users must deposit more Bitcoin value than the $YU they mint, creating a buffer against market volatility. For example, with a 110% collateralization requirement, a user depositing $110 worth of Bitcoin could mint up to $100 in $YU. This over-collateralization creates a security margin that absorbs price fluctuations in Bitcoin while maintaining the stability of $YU. The protocol dynamically tracks both individual position health and the total collateralization ratio of the system, intervening through liquidation mechanisms when necessary to maintain system-wide stability.

### Peg Stability

$YU maintains its soft peg to the US dollar through a multi-faceted approach implemented across several contracts. The primary stability mechanism is the liquidation system, which automatically resolves undercollateralized positions when they fall below the Minimum Collateralization Ratio. The TroveManager implements a two-tier liquidation process: positions are first liquidated against the StabilityPool, with any remainder distributed to other Trove holders. This process ensures that undercollateralized debt is efficiently removed from the system, maintaining adequate collateralization. Complementing this, the PSM (Peg Stability Module) contract enables direct conversion between $YU and other stablecoins with minimal slippage, creating arbitrage opportunities that help maintain the peg. The protocol also implements stability fees through the interest rate mechanism, which can be adjusted by governance to influence $YU supply. During periods when $YU trades below its peg, higher stability fees discourage minting and encourage debt repayment, reducing supply and supporting the price. Conversely, when $YU trades above its peg, lower fees can stimulate supply expansion. The StabilityPool further enhances stability by serving as a buffer for liquidations and providing a mechanism for yield distribution that encourages users to hold and lock $YU, thereby reducing market volatility.



