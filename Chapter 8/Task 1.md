HC8T1

* Defines the type synonyms `Address` and `Value`
* Implements the function `generateTx`
* Includes a `main` function to run and test it

```haskell
-- Define type synonyms
type Address = String
type Value = Int

-- Define the function that generates a transaction string
generateTx :: Address -> Address -> Value -> String
generateTx fromAddr toAddr val =
  "From: " ++ fromAddr ++ " -> To: " ++ toAddr ++ " | Value: " ++ show val

-- Main function to run the code
main :: IO ()
main = do
  let sender = "addr1qxy..."
  let receiver = "addr1qabc..."
  let amount = 100
  let transaction = generateTx sender receiver amount
  putStrLn "Generated Transaction:"
  putStrLn transaction
```

### What this does:

* Uses `type` to define clear, readable aliases.
* Formats the transaction as a human-readable string.
* Outputs the result when run.

### Sample output when run:

```
Generated Transaction:
From: addr1qxy... -> To: addr1qabc... | Value: 100
```


