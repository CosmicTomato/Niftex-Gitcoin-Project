# Niftex-Gitcoin-Project
created for https://gitcoin.co/issue/metalithio/niftex-gr8-hackathon/1/100024098

This is a minimal ERC20 Token based on OpenZeppelin contracts that is "capped, mintable, burnable and pausable" as defined in the above linked page, paired with an eip-1167 minimal proxy implementation to reduce gas costs of deploying many ERC20 contracts.

Deployment flow is as follows:
1) A copy of Contract NiftexERC20 is deployed

2) A copy of Contract NiftexERC20Factory is deployed, with the address of the above contract as the constructor argument

3) Any additional ERC20 contracts can be deployed by the owner of the contract created in step (2), by calling function "deploy" with appropriate arguments
(as implemented these are the token name, symbol, max number of tokens i.e. "mintLimit", and the desired owner of the new contract, although the contract can easily be modified to include more arguments)


Tested on Remix (https://remix.ethereum.org/) the reported gas costs are:

2400206 gas transaction cost (1741774 gas execution cost) for step (1) deployment of NiftexERC20

823720 gas transaction cost (579796 gas execution cost) for step (2) deployment of NiftexERC20Factory

162412 gas transaction cost (138068 gas execution cost) for step (3) deployment of new NiftexERC20 contract through call to "deploy" function of NiftexERC20Factory contract
