HC5T7: The $ Operator

---

### ✅ Rewritten with `$` Operator:

```haskell
-- Use $ to avoid parentheses
result :: Int
result = sum $ map (*2) $ filter (>3) [1..10]

-- Main function to print the result
main :: IO ()
main = do
    putStrLn $ "The result is: " ++ show result
```

---

### 🛠 How to Run:

1. Save this as `DollarOperator.hs`
2. Compile and run:

   ```bash
   ghc DollarOperator.hs -o dollar
   ./dollar
   ```

---

### 🔍 Expected Output:

```
The result is: 84
```

### 💡 Why `$` is useful:

It allows you to **eliminate nested parentheses** by making function application **right-associative**.
This line:

```haskell
sum (map (*2) (filter (>3) [1..10]))
```

becomes:

```haskell
sum $ map (*2) $ filter (>3) [1..10]
```


