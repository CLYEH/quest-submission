# Chapter 2 Day 4 - Basic Structs

1. Deploy a new contract that has a Struct of your choosing inside of it (must be different than Profile).
2. Create a dictionary or array that contains the Struct you defined.
3. Create a function to add to that array/dictionary.
4. Add a transaction to call that function in step 3.
5. Add a script to read the Struct you defined.

For Q1~Q3:
```Cadence
pub contract Wallet { // assume this contract deployed on 0x02

    pub let walletBalance: {Address: Balance}

    pub struct Balance {
        pub let btc: Int
        pub let eth: Int
        pub let flow: Int
        pub let account: Address

        init(_btc: Int, _eth: Int, _flow: Int, _account: Address) {
            self.btc = _btc
            self.eth = _eth
            self.flow = _flow
            self.account = _account
        }
    }

    pub fun addAccount (btc: Int, eth: Int, flow: Int, account: Address) {
        let newAccount = Balance(_btc: btc, _eth: eth, _flow: flow, _account: account)
        self.walletBalance[account] = newAccount    
    }

    init(){
        self.walletBalance = {}
    }
}
```
For Q4:
```Cadence
import Wallet from 0x02

transaction(btc: Int, eth: Int, flow: Int, account: Address) {

    prepare(signer: AuthAccount) {}
    
    execute {
    
        Wallet.addAccount(btc: btc, eth: eth, flow: flow, account: account)
        log("Done!")
    }

}
```

For Q5:
```Cadence
import Wallet from 0x02

pub fun main(account: Address): Wallet.Balance {
    return Wallet.walletBalance[account]!
}
```
