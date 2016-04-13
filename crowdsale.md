# The crowdsale idea


# What slock.it is planning

This is what I understand as of this moment from the [whitepaper](https://download.slock.it/public/DAO/WhitePaper.pdf), the [slockit site](https://slock.it/dao.html), their [github repo](https://github.com/slockit/DAO) and some reddit disscussions.

### about the money

1. The DAO is an  entity with no formal ties to slock.it (apart from the fact that they are developing and promoting it)
1. The DAO is a generic "investment vehicle"
1. So they are not selling slock.it; nor is slockit raising money that it can use directly. I think 'what's in it for them' is limited to the assumption that the DAO will be owned by people interested in having slockit as the DAO's main 'service provider' - i.e. that the DAO will choose to invest or buy things from slock.it.

### about the protocol

1. The governance of the DAO is directly related to the ownership tokens: 1 token=1 vote. (No backfeed-style reputation layer) 
1. They give a lot of attention to the '51% attack' (meaning in this case that a majority can vote to give all the money to themselves, effectively stealing the remaining 49% of the funds). Their solution: all proposals must be passed through a 'curator' that is responsable for curating a white list of 'service providers', and money can be transferred only to the whitelist. In addition, the decision procedure is (I think) deliberately long to give users time to detect problems. The DAO can decide to change the curator, and if it disagrees, it can fork.
1. There is the concept of 'reward tokens' that I think is very interesting. They are not really explained in the whitepaper and have no real function in the reference implementation, as far as i could see scanning it quickly. But the idea is that they represent a claim on the future profits/dividents of investments, and so, in the case of forking, not only ownership tokens are divided, but also the claims on future revenue.

### about the 'software ecosystem'

For a DAO like this to be functioning as a comunity, one needs a lot of off-blockchain functionality. DAO owners will need some kind of interface to make buy DAO tokens, make proposals, discuss the proposals, vote on them, and keep track of which money is invested where. In other words, a wallet, a website, a discussion forum of some type.

1. I have not found any discussion/communication of slockit about this.
1. There is some code on github with an interface for the crowdsale [https://github.com/slockit/tokensale](https://github.com/slockit/tokensale)
1. Their 'software stack':
    1. the contract is written in solidity
    1. the tokensale contract in node/javascript.
    2. they use [gatecoin](https://gatecoin.com/) to interface with the blockchain
    

