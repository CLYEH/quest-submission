# Quest-Submission

## Chapter 1 - Day 1 - Learning Blockchain Concepts

### 1. Explain what the Blockchain is in your own words. You can read this to help you, but you don't have to: https://www.investopedia.com/terms/b/blockchain.asp

A blockchain is a decentralized database which is accessable and open to all. The data on the blockchain is stored distributed in every node on the computer network and each node stores the same copy of the data which means there is no central authority to manage the data. Once the data has been recorded on chain, the data only changed if the owner approves to. The mechanism of it is that blockchain technology uses a cryptography method of public key and private key which only allows the corresponding private key to access the data. So as the owner keeps his key safe, it is nearly impossible to undone any of his data by any others.  

### 2. Explain what a Smart Contract is. You can read this to help you, but you don't have to: https://www.ibm.com/topics/smart-contracts

A smart contract is a series of code that could be deployed by anyone on the blockchain. The contract can be called by any user to execute the specific action on chain, which could take paramaters input by users, record any valid data on the chain and will update the data to every node.
  
### 3. Explain the difference between a script and a transaction.

- A **script** is used to view blockchain data which does not change any status on chain and doesn't cost money.
- A **transaction** is a function call that could change the data on chain and requires fee.


## Chapter 1 - Day 2 - The Flow Blockchain & Cadence

### 1. What are the 5 Cadence Programming Language Pillars?

1. **Safety and Security**: An execution of smart contract is of concern of user's money, so the safety and security is the first thing of the programming language. Cadence is designed to be a strong static type system that developers could identify bugs at the early stage of development. This design could effectively improve the safety and security of smart contract.
2. **Clarity**: Cadence is very easy to read as users can audit the saffety of smart contract by theirselves.
3. **Approachability**: The written of Cadence is similar to other program language which any experienced developers could be very easy to get started.
4. **Developer Experience**: Debugging is sometimes agony for developers. The error message in Cadence is very clear for debugging.
5. **Resource Oriented Programming**: Cadence is a resource oriented programming language that allows assets on Flow chain record on the user's address, not like Ethereum, tokens are stored in a contract that record the status of the token.

### 2. In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful (you don't have to answer this for #5)?

These pillars could be referenced for every project or product. As a user of a product, the most crucial thing is that if it is safe to use. Secondly, if the instruction of product is clarity enough or easy to operate. For the developer, is it easy to maintain the product is important.

## Chapter 2 - Day 1 - Our First Smart Contract

### 1. Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed.

```
pub contract JacobTucker {
    pub let is: String
    
    init() {
        self.is = "The Best"
    }
}
```

### 2. Check that your variable is actually equals "the best" by executing a script to read that variable. Include a screenshot of the output.

```
import JacobTucker from 0x03

pub fun main(): String {
    return JacobTucker.is 
}
```

Result:

![Result](https://github.com/CLYEH/quest-submission/blob/main/CH2_D1_Q2.png?raw=true)
