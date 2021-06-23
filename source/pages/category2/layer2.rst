Layer 2
========

Background
----------
During the research and development phases of AquaFi we constantly analysed the layer 2 landscape to ensure maximum success for the protocol. We recognise that transactions fees on the Ethereum main-net may continue to rise over time thus making the protocol unusable for smaller stakes.

We analysed many different solutions to get AquaFi onto layer 2:

- Force the user to migrate their liquidity from L1 to L2 and then accept the stake (all within a single transaction and transparently via the UI)
- Launch AquaFi with support for pre-determined L2 solutions - eg Arbitrum and/or Optimism
- Create a token bridge when needed in the future upon L2 deployment
- Add support to the Aqua token to allow updating of the minter addresses

Each of these solutions has its advantages and disadvantages. The main disadvantages being:

- additional development work
- having to know and permanently finalise the L2 networks to support upon Aquafi launch
- enabling additional minters 
- traditional token bridges only work for tokens that do not have a minting functionality

Finalised Approach
------------------
The solution we eventually decided on was to add support to the Aqua token which would allow the Blockzero council to update the minter addresses. This will allow us to have the flexibility of creating a token bridge and whitelisting the token bridge address on the Aqua token for a true 1 to 1 Aqua exchange between layer 1 and layer 2.

This was proposed to the community and approved by nearly 90% of all XIO holders agreeing with the solution, additional information about this can be `found here <https://vote.blockzerolabs.io/#/blockzerolabs.eth/proposal/QmZGddNkbmfymwTfuqdWmHpd3Zed8UEVoMTijwCEfiTf9A>`_
.