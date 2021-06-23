KPI Options
===========

Background
----------

There was much discussion in the community over the duration of development regarding a proposal originally submitted by AllStuffCrypto. This proposal consisted of airdropping Aqua tokens to the target market of AquaFi - liquidity providers in the hope this would serve as a good marking campaign to draw attention to the protocol.

This idea eventually morphed into designing KPI Option tokens which allow recipients to either immediately liquidate their option tokens for Aqua **or** help AquaFi by adding value which increases the value of said options.

KPI Token Information
---------------------
We have decided to utilise 20% of the total supply of Aqua towards these KPI Option tokens. We will deposit this into a smart contract and mint 100,000 Option tokens. The value/exchange rate of these options tokens will be based on the Total Fees Captured KPI Metric. This means as the total fees captured by the protocol increases, these KPI Option tokens will also increase in value since they will be redeemable for more Aqua tokens.

The format of these options tokens will be as follows:

- Total Fees Captured: >= $0,       1 KPI Option = 0 Aqua
- Total Fees Captured: >= $250,000, 1 KPI Option = 0.25 Aqua
- Total Fees Captured: >= $500,000, 1 KPI Option = 0.5 Aqua
- Total Fees Captured: >= $750,000, 1 KPI Option = 0.75 Aqua
- Total Fees Captured: >= $1,000,000, 1 KPI Option = 1 Aqua

These options tokens will be using a linear scale rather than unlocking at each fee level. This means if the total fees captured is $100,000, the options tokens can be exchanged for 0.1 Aqua tokens. We decided to use a linear scale to help subdue the downward pressure if recipients decide to liquidate their option tokens.

The KPI Metric "Total Fees Captured" will be updated by the Blockzero council to avoid any tampering or exploits which is something that may be present with on-chain calculations. The option to switch to a on-chain calculation will exist through governance but additional development work will need to be undertaken for this functionality.

The estimated number of Aqua tokens allocated to KPI Options is 150 million.

Options Distribution
--------------------

We will initially distribute 50% of all KPI Options upon launch (or shortly after) of AquaFi. The Blockzero council will retain control of the remaining 50% and release these as new DEX's and/or projects are added to AquaFi. These remaining 50% of KPI option tokens will be kept in the Vortex until they are voted on to be used to help incenticise additional DEXs.

Example: If AquaFi supports Curve Finance LP tokens in the coming months after the initial deployment then these reserved KPI Option tokens could be used to help incentivise Curve LPs to add their Curve LP tokens into AquaFi.

Options Deadlines
-----------------

The initial distribution will be valid for upto three months after they are initially uploaded into Dropzero (available for claiming). This means the original recipients will have three months to claim their Aqua KPI Option tokens from Dropzero before they are returned to the Vortex.

These KPI Option tokens will be redeemable until the end of the ethereum blockchain. However, if the total fees captured does not hit $1,000,000 USD by **XXXXXXXXX** date then the value of the options at this date will be the permanent value. This means if the total fees generated is $900,000 by the aforementioned date, then regardless of the KPI increasing (total fees generated), these option tokens will still be exchangeable for 0.9 Aqua tokens. **Please note, this is subject to how the KPI Option token from UMA works and is therefore subject to the same limitations.**