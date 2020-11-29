# Niftex-Gitcoin-Project
created for https://gitcoin.co/issue/metalithio/niftex-gr8-hackathon/1/100024098

This is a minimal ERC20 Token based on OpenZeppelin contracts that is "capped, mintable, burnable and pausable" as defined in the above linked page.

Deployment flow is as follows:
1) A copy of Contract NiftexERC20 is deployed
2) A copy of Contract NiftexERC20Factory is deployed, with the address of the above contract as the constructor
3) Any additional ERC20 contracts can be deployed by the owner of the contract created in step 2, by calling function "deploy" with appropriate arguments
(as implemented these are the token name, symbol, max number of tokens i.e. "mintLimit", and the desired owner of the new contract, although the contract can easily be modified to include more arguments)
