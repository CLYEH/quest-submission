# Chapter 3 Day 1 - Resources

## 1. In words, list 3 reasons why structs are different from resources.

A Struct and a resource are both containers storing data, but the differences between them:

- data in a struct can be copied, but not in a resource
- data in a struct can be created as many as you want, but can only be created once in a resource
- Once a struct has been created, it can be overwritten, but it is not allowed to overwite a resource

## 2. Describe a situation where a resource might be better to use than a struct.

While you want to create a thing with a limited amount and might be transferring.

## 3. What is the keyword to make a new resource?

`create`

## 4. Can a resource be created in a script or transaction (assuming there isn't a public function to create one)?

No, it can only be created in a contract.

## 5. What is the type of the resource below?

```Cadence
pub resource Jacob {
}
```

The tyoe if the resource is `Jacob`.

## 6. Let's play the "I Spy" game from when we were kids. I Spy 4 things wrong with this code. Please fix them.

```Cadence
pub contract Test {
    // Hint: There's nothing wrong here ;)
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }
    pub fun createJacob(): Jacob { // there is 1 here
        let myJacob = Jacob() // there are 2 here
        return myJacob // there is 1 here
    }
}
```

My answer:

```Cadence
pub contract Test {
    // Hint: There's nothing wrong here ;)
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }
    pub fun createJacob(): @Jacob {
        let myJacob <- create Jacob()
        return <- myJacob
    }
}
```
