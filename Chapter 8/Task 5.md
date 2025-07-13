HC8T5

* Defines a `Person` type using **record syntax** with fields: `name`, `age`, and `isEmployed`
* Creates two people: `person1` (employed) and `person2` (unemployed)
* Includes a `main` function that prints both people's details

```haskell
-- Define the Person type using record syntax
data Person = Person
  { name        :: String
  , age         :: Int
  , isEmployed  :: Bool
  } deriving Show

-- Create an employed person
person1 :: Person
person1 = Person
  { name = "Alice"
  , age = 30
  , isEmployed = True
  }

-- Create an unemployed person
person2 :: Person
person2 = Person
  { name = "Bob"
  , age = 25
  , isEmployed = False
  }

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Person 1:"
  print person1

  putStrLn "\nPerson 2:"
  print person2
```

### Sample output:

```
Person 1:
Person {name = "Alice", age = 30, isEmployed = True}

Person 2:
Person {name = "Bob", age = 25, isEmployed = False}
```


