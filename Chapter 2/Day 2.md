# Chapter 2 Day 2 - Transactions and Scripts

## 1. Explain why we wouldn't call `changeGreeting` in a script.

'changeGreeting' is a function in the contract that updates a new value, but a script does not write or change any data on the blockchain, instesd, it can only view.

## 2. What does the `AuthAccount` mean in the `prepare` phase of the transaction?

`AuthAccount` is a type in Cadence. By assigning an `AuthAccount` type signer in the `prepare` phase, the user who executes the transaction will need to sign and approve the transaction to access the signer's data needed for the transaction.

## 3. What is the difference between the `prepare` phase and the `execute` phase in the transaction?

- In a `prepare` phase, the transaction will access data in the user account needed for transaction.
- In a `execution` phase, the the transaction can call functions in a contracts and modify or write data on the blockchain. 

## 4. This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.

- Add two new things inside your contract:
  - A variable named `myNumber` that has type `Int` (set it to 0 when the contract is deployed)
  - A function named `updateMyNumber` that takes in a new number named `newNumber` as a parameter that has type `Int` and updates `myNumber` to be `newNumber`
- Add a script that reads `myNumber` from the contract
- Add a transaction that takes in a parameter named `myNewNumber` and passes it into the `updateMyNumber` function. Verify that your number changed by running the script again.

The contract deployed by `0x02`:
```Cadence
pub contract CH2_D2_Q4 {
  pub var myNumber: Int
  pub fun updateMyNumber(newNumber: Int) {
    self.myNumber = newNumber
  }
  init() {
    self.myNumber = 0
  }
}
```

The script:
```Cadence
import CH2_D2_Q4 from 0x02
pub fun main() : Int {
  return CH2_D2_Q4.myNumber
}
```

The transaction:
```Cadence
import CH2_D2_Q4 from 0x02
transaction(myNewNumber: Int) {
  prepare(signer: AuthAccount) {}
  
  execute {
    CH2_D2_Q4.updateMyNumber(newNumber: myNewNumber)
  }
}
```
