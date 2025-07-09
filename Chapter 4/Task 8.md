HC4T8 - Task 8: Extract Values from Tuples

---

### ✅ Haskell Code:

```haskell
-- Define describeTuple to extract and describe a 2-element tuple
describeTuple :: (Show a, Show b) => (a, b) -> String
describeTuple (x, y) = "The first value is " ++ show x ++ " and the second value is " ++ show y ++ "."

-- Main function to test describeTuple
main :: IO ()
main = do
    putStrLn $ describeTuple (42, "Haskell")
    putStrLn $ describeTuple ("Hello", True)
    putStrLn $ describeTuple (3.14, 100)
```

---

### 🛠 How to Run

1. Save the code in a file, e.g., `DescribeTuple.hs`
2. Compile and run it:

   ```bash
   ghc DescribeTuple.hs -o describetuple
   ./describetuple
   ```

---

### 🔍 Expected Output:

```
The first value is 42 and the second value is "Haskell".
The first value is "Hello" and the second value is True.
The first value is 3.14 and the second value is 100.
```

---


