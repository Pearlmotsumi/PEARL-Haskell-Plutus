HC10T9: MinMax Type Class

* Defines a type class `MinMax` with methods `minValue` and `maxValue`,
* Implements it for the type `Int`,
* Includes a `main` function to demonstrate the usage.

---

### ✅ Haskell Code

```haskell
-- Define the MinMax type class
class MinMax a where
  minValue :: a
  maxValue :: a

-- Instance for Int
instance MinMax Int where
  minValue = minBound
  maxValue = maxBound

-- Main function to demonstrate
main :: IO ()
main = do
  putStrLn $ "Min Int: " ++ show (minValue :: Int)
  putStrLn $ "Max Int: " ++ show (maxValue :: Int)
```

---

### 📝 Explanation

* The `MinMax` class provides `minValue` and `maxValue` without parameters.
* For `Int`, we use `minBound` and `maxBound` which come from the `Bounded` type class.
* In `main`, we explicitly annotate the type to `Int` when calling `minValue` and `maxValue`.

