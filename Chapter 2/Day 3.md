# Chapter 2 Day 3 - Arrays, Dictionaries, and Optionals

## 1. In a script, initialize an array (that has length == 3) of your favourite people, represented as `String`s, and `log` it.

```Cadence
pub fun main(){
  var favppl: [String] = ["Satoshi","Vitalic","Elon"]
  log(favppl)
}
```

## 2. In a script, initialize a dictionary that maps the `String`s Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a `UInt64` that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!

```Cadence
pub fun main(){
  var socialmedia: {String: UInt64} = {"Facebook":3 , "Instagram":2 , "Twitter":1 , "YouTube":4 , "Reddit":5 , "LinkedIn":0 }
}
```

## 3. Explain what the force unwrap operator `!` does, with an example different from the one I showed you (you can just change the type).

An optional type `Type?` variable is either a value with the `Type` or `nil`. The force unwrap operator `!` can uwrap `Type?` to either `nil` or `Type`, depending on what value the variable is.

The example:
```Cadence
pub fun main(){
  var account1: Int? = 1234
  var unwrappedacc1 = account1!
} // Result > {"type":"Void"}
```

```Cadence
pub fun main(){
  var account2: Int? = nil
  var unwrappedacc2 = account2!
} // Error > unexpectedly found nil while forcing an Optional value
```

## 4. Using this picture below, explain...

- What the error message means
- Why we're getting this error
- How to fix it

![Q4](https://github.com/emerald-dao/beginner-cadence-course/raw/main/chapter2.0/images/wrongcode.png)

The error message means the return type is not matching the type that we declared in the first line, as we declared a `String` type but returning a `String?` type.

This script is gonna return a value from a dictionary, but as long as we want to access the value of a dictionary, it will always return an optional type value, but at the first line of the script, the main() function has been declared as a `String` type, which will be an error if executed.


