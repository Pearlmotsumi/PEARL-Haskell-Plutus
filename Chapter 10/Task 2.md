HC10T2: Summable Type Class

1. Defines a **type class** `Summable` with a function `sumUp :: [a] -> a`.
2. Implements `Summable` for the `Int` type.
3. Demonstrates it in the `main` function.

---

### ✅ Haskell Code

```haskell
-- Define the Summable type class
class Summable a where
  sumUp :: [a] -> a

-- Implement Summable for Int
instance Summable Int where
  sumUp = sum

-- Main function to demonstrate usage
main :: IO ()
main = do
  let numbers = [1, 2, 3, 4, 5]
  putStrLn $ "The sum is: " ++ show (sumUp numbers)
```

---

### 🟢 Sample Output

```
The sum is: 15
```
