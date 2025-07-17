HC10T3: Comparable Type Class

1. Define a custom data type `Blockchain`.
2. Define a type class `Comparable` with a method `compareWith`.
3. Implement `Comparable` for `Blockchain`, using block height (or a made-up value for ordering).

---

### ✅ Haskell Code

```haskell
-- Define the Blockchain data type
data Blockchain = Blockchain { name :: String, blocks :: Int }

-- Define a custom type class Comparable
class Comparable a where
  compareWith :: a -> a -> Ordering

-- Implement Comparable for Blockchain based on number of blocks
instance Comparable Blockchain where
  compareWith b1 b2 = compare (blocks b1) (blocks b2)

-- Show instance to display Blockchain nicely
instance Show Blockchain where
  show (Blockchain n b) = n ++ " with " ++ show b ++ " blocks"

-- Main function
main :: IO ()
main = do
  let cardano = Blockchain "Cardano" 8000
  let ethereum = Blockchain "Ethereum" 16000
  let comparison = compareWith cardano ethereum

  putStrLn $ "Comparing:\n  " ++ show cardano ++ "\n  " ++ show ethereum
  putStrLn $ "Result: " ++ show comparison
```

---

### 🟢 Sample Output

```
Comparing:
  Cardano with 8000 blocks
  Ethereum with 16000 blocks
Result: LT
```

### 🔎 Notes

* The `Ordering` result will be `LT`, `EQ`, or `GT`, depending on how many blocks each blockchain has.
* You can easily extend `Comparable` to other types (e.g., people, tokens, etc.).

