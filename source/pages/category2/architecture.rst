Architecture
============

Here at Blockzero Labs we have learnt a significant amount from the development process and architecture of the `Flash protocol <https://flashstake.io>`_
. This is why we decided to ensure AquaFi was designed in the most upgradable way possible from the beginning. It is due to this reason we followed a highly modular design for the protocol.

These modules can be upgraded/modified after the initial launch to extend or change the functionality. This is possible via governance and will require the Blockzero multi-sig wallet and a time delay to approve such a change - more information can be found on the governance section of this documentation.

**[architecture diagram for better illustration here]**

The AquaFi protocol can be broken down into the following discrete pieces:

- Aqua Primary Contract: This module is responsible for bringing together the other modules of AquaFi. This contract specifies what handlers are allowed to interact with the Aqua Primary as well as additional functionality such as Stake, Unstake and Unstake all.
- Oracle Contract: This module is responsible for obtaining the price of the Aqua token in a decentralised manner. We currently have two separate implementations of this, one which uses the time-weighed-average-price (TWAP) oracle from Uniswap Version 2 and one which uses the same oracle but with Uniswap Version 3.
- Handler Contracts: These "handler" contracts are responsible for supporting a specific decentralised exchange such as Uniswap V2. The purpose of this feature is to integrate the exchanges with aqua prtotocol Upon launch, we intend to launch with the following handler contracts: Uniswap V2, Uniswap V3, Flashstake and Sushiswap.
- Index Fund Contract: This module is responsible for dispatching the tokens requested by the users against the aqua token they hold. It calculates the equivalent amount of tokens to be dispatched on the basis of the aqua token percentage they provide. After transfering the tokens, this contract burns the aqua token of that user thus decreasing the aqua total supply and increasing the value of the token. The contract aquires 2% of the tokens in every unstake.  

**Aqua Primary Contract**
---------------------
The primary contract consists of some generalized components that ensures the integration with different exchanges like uniswap,sushiswap and others.

**Stake**
---------------------

Parameters: (uint256 tokenIdOrAmount,address handlerAddress,address contractAddress,bytes data)

Description: This function is responsible for staking the users lp token and transfer it to handler contract. It updates the stakes record and invokes the handlers update function where the rootK value of the lp token is calculated and saved in the stakes record. 


**Unstake**
---------------------

Parameters: (bytes32[] calldata id, uint256[] calldata tokenValue)

Description: This function is responsible for unstaking the lp tokens. It iterates through the list of lp tokens and calculates the cummulative fees in aqua token from all the lp tokens. This function fetches the fees by calling the internal function _unstake in which which expects single id and tokenValue and returns the aqua amount in terms of fees accumulated for that token. Inside the function it fetches the token difference, aqua premium and token address by calling the withdraw function of the selected handler. Then on the basis of aqua price fetched from the oracle, it calculates the aqua amount which is then added to the fees calculated on the basis of aqua premium.

---------------------

**Oracle Contract**
---------------------

This contract is responsible for fetching the price of a provided token address with respect to aqua token. It only works for pair who has pair with WETH.

**Fetch**
---------------------
Parameters: (address token, bytes32 data)

Description: This function is responsible for fetching the amount of aqua per token provided.

**FetchAquaPrice**
---------------------
Prameters: (no params)

Description: This funciton retireves aqua price in terms of eth i.e one eth is equal to x aqua.

---------------------

**Handler Contract**
---------------------

There are different handler contracts specific to the exchanges and their respective logic, each handler contract makes sure the interaction with aqua primary contract and allow only aqua primary contract to access its functions to perform the aqua protocol specific operations.

- Handlers with ERC20 lp tokens (uniswap v2, sushiswap, flashstake etc)

- Handlers with ERC721 lp tokens "nfts" (uniswap v3)

**V2 Handler Functions**
---------------------
The major v2 handler functions are as follows.

**Update**
---------------------

Parameters: (bytes32 stakeId,uint256 lpAmount,address lpToken,bytes calldata data)

Description: It stores the rootk (K = root(token0 * token1)) against the lpToken that has been staked. It is only callable by the primary contract. It decodes the staker and pool address from the encoded data param. If the pool is whitelisted and the stake does not already exists then it finds the rootK value of the lpToken and saves the required stake data in the mapping.

**Withdraw**
---------------------

Parameters: (bytes32 id, uint256 tokenIdOrAmount, address contractAddress)

Description: Calculates the rootK difference to see if any fees has been accumulated. If so, it only pays the lp amount back to the user and returns fees in token0 & token1 back to aqua primaty contract from where aqua gets paid out. Index fund reieves lp token. It is only callable by the primary contract, it returns tokenAddress, premium, tokenDifference and ecoded data of premium, tokenAddress and tokenFess acumulated.Once it is done then it deletes the stake entry from the storage.

**V3 Handler Functions**
---------------------

The major v3 handler functions are as follows.

**Update**
---------------------

Parameters: (bytes32 id, uint256 tokenValue, address contractAddress, bytes32 data)

Description: It checks the fees against the nft, if the fees exists then it updates the fees in the user stakes record. It does so by first decoding the pool address from the encoded data recieved from the params. It checks if the pool is whitelisted if yes then it updates the token0AtDeposit and token1AtDeposit by fetching it from nftPositionManager positions on the basis of tokenValue recieved in the params. This function is only callable from Aqua Primary Contract.

**Withdraw**
---------------------

Parameters: (bytes32 id, uint256 tokenIdOrAmount, address staker, address contractAddress)

Description: This function sends the lp tokens back to the staker and sends the fees in token0 and token1 accumulated to index fund. It returns fees in token0 & token1 bacck to aqua primaty contract from where aqua gets paid out. 







