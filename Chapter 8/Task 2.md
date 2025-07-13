HC8T2

* Defines a `PaymentMethod` data type with three constructors: `Cash`, `Card`, and `Cryptocurrency`
* Defines a `Person` data type with a `name`, `address` (a tuple of `String` and `Int`), and a `paymentMethod`
* Creates a `Person` instance named `bob` who pays with `Cash`
* Includes a `main` function that prints Bob’s details

```haskell
-- Define the PaymentMethod data type
data PaymentMethod = Cash | Card | Cryptocurrency deriving Show

-- Define the Person data type
data Person = Person
  { name          :: String
  , address       :: (String, Int)
  , paymentMethod :: PaymentMethod
  } deriving Show

-- Create an instance of Person named bob
bob :: Person
bob = Person
  { name = "Bob"
  , address = ("Main Street", 42)
  , paymentMethod = Cash
  }

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Person Details:"
  print bob
```

### Sample output when run:

```
Person Details:
Person {name = "Bob", address = ("Main Street",42), paymentMethod = Cash}
```


