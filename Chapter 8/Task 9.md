HC8T9

* Defines type synonyms `Address` and `Value`
* Defines a `Transaction` record type with fields: `from`, `to`, `amount`, and `transactionId`
* Implements a function `createTransaction` that creates a `Transaction` and returns the transaction ID (for simplicity, it generates a transaction ID as a concatenation of the addresses and amount)
* Includes a `main` function to demonstrate usage

```haskell
-- Type synonyms
type Address = String
type Value = Int

-- Transaction data type
data Transaction = Transaction
  { from          :: Address
  , to            :: Address
  , amount        :: Value
  , transactionId :: String
  } deriving Show

-- Function to create a Transaction and return the transactionId
createTransaction :: Address -> Address -> Value -> String
createTransaction fromAddr toAddr val =
  let txId = fromAddr ++ "_to_" ++ toAddr ++ "_amt_" ++ show val
      _transaction = Transaction
        { from = fromAddr
        , to = toAddr
        , amount = val
        , transactionId = txId
        }
  in txId

-- Main function to run the code
main :: IO ()
main = do
  let sender = "addr1abc"
      receiver = "addr1xyz"
      value = 250
      txId = createTransaction sender receiver value
  putStrLn $ "Created transaction with ID: " ++ txId
```

### Sample Output:

```
Created transaction with ID: addr1abc_to_addr1xyz_amt_250
```

