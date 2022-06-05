# Chapter 2 - Day 1 - Our First Smart Contract

## 1. Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed.

```
pub contract JacobTucker {
    pub let is: String
    
    init() {
        self.is = "The Best"
    }
}
```

## 2. Check that your variable is actually equals "the best" by executing a script to read that variable. Include a screenshot of the output.

```
import JacobTucker from 0x03

pub fun main(): String {
    return JacobTucker.is 
}
```

Result:

![Result](https://github.com/CLYEH/quest-submission/blob/main/CH2_D1_Q2.png?raw=true)
