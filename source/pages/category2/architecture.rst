Architecture
============

Here at Blockzero Labs we have learnt a significant amount from the development process and architecture of the `Flash protocol <https://flashstake.io>`_
. This is why we decided to ensure AquaFi was designed in the most upgradable way possible from the beginning. It is due to this reason we followed a highly modular design for the protocol.

These modules can be upgraded/modified after the initial launch to extend or change the functionality. This is possible via governance and will require the Blockzero multi-sig wallet and a time delay to approve such a change - more information can be found on the governance section of this documentation.

The AquaFi protocol can be broken down into the following discrete pieces:

- Aqua Primary Contract: This module is responsible for bringing together the other modules of AquaFi. This contract specifies what handlers are allowed to interact with the Aqua Primary as well as additional functionality such as ......
- Oracle Contract: This module is responsible for obtaining the price of the Aqua token in a decentralised manner. We currently have two separate implementations of this, one which uses the time-weighed-average-price (TWAP) oracle from Uniswap Version 2 and one which uses the same oracle but with Uniswap Version 3.
- Handler Contracts: These "handler" contracts are responsible for supporting a specific decentralised exchange such as Uniswap V2. The purpose of this function is to ......... Upon launch, we intend to launch with the following handler contracts: Uniswap V2, Uniswap V3, Flashstake and Sushiswap.
- **Are there any more pieces here? Xord to advise.**

Aqua Primary Contract
---------------------
Detailed information about the primary contract - Xord to advise


Oracle Contract
---------------------
Detailed information about the primary contract - Xord to advise


Handler Contract
---------------------
Detailed information about the primary contract - Xord to advise

