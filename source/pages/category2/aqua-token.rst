Aqua Token
============

The Aqua token is the utility token that will be used within AquaFi to pay premiums to users. The AquaFi protocol will capture liquidity from staked tokens and upon unstaking, the user will be paid their fees with newly minted Aqua tokens.

Contract Addresses
------------------
This token has been deployed on both test-net and the Ethereum main-net.

- [Mainnet] 0xd34a24006b862f4e9936c506691539d6433ad297
- [Rinkeby] 0xB2dc7059D7c9c2b93E924dc7C938FcbF986aC5C2


Contract Functionality
----------------------
The Aqua token conforms to the ERC20 token standard which means the following functionality is supported:

- Mint
- Burn
- Transfer
- TransferFrom
- BurnFrom

Aqua Token Privileges
----------------------
The Aqua token will allow users to:

- Have governance rights over almost all AquaFi related proposals and almost all AquaFi related decisions - e.g. change pool premiums - the exhaustive list is as follows:

  - Governance will be executed through timelock contract.
  
  - Base premium can be decided by the aqua community.
  
  - Updating oracle address, hander addresses, locking and unlocking of handler contracts.
  
  - Grant/Revoke Minting roles to addresses.
  
  - Allows users to burn aqua tokens to redeem fees from indexfund contract. Eg, If users burns 10% of the aqua tokens then users can withdraw 10% off underlying assests in the indexfund.
