HC5T4: Using Lambda Functions

---

### ✅ Haskell Code Using a Lambda:

```haskell
-- Define biggerThan10 using a lambda function
biggerThan10 :: Int -> Bool
biggerThan10 = \x -> x > 10

-- Main function to test biggerThan10
main :: IO ()
main = do
    print $ biggerThan10 5     -- False
    print $ biggerThan10 10    -- False
    print $ biggerThan10 15    -- True
```

---

### 🛠 How to Run:

1. Save the code in a file, e.g., `LambdaBiggerThan10.hs`
2. Compile and run it:

   ```bash
   ghc LambdaBiggerThan10.hs -o lambdaTest
   ./lambdaTest
   ```

---

### 🔍 Expected Output:

```
False
False
True
```


