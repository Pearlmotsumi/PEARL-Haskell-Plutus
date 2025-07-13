HC8T8

* Defines type synonyms `Name` for `String` and `Age` for `Int`
* Implements a function `greet :: Name -> Age -> String` that returns a greeting
* Uses the function in `main` with sample input

```haskell
-- Type synonyms
type Name = String
type Age  = Int

-- Greeting function
greet :: Name -> Age -> String
greet name age = "Hello, " ++ name ++ "! You are " ++ show age ++ " years old."

-- Main function to run the code
main :: IO ()
main = do
  let personName = "Alice"
  let personAge = 28
  putStrLn (greet personName personAge)
```

### Sample Output:

```
Hello, Alice! You are 28 years old.
```

