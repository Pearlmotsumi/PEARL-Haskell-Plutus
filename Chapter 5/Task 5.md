HC5T5: Partial Application

---

### ✅ Haskell Code:

```haskell
-- Define multiplyByFive using partial application
multiplyByFive :: Int -> Int
multiplyByFive = (5 *)

-- Main function to test multiplyByFive
main :: IO ()
main = do
    print $ multiplyByFive 2    -- 10
    print $ multiplyByFive 10   -- 50
    print $ multiplyByFive (-3) -- -15
```

---

### 🛠 How to Run:

1. Save this code in a file, e.g., `MultiplyByFive.hs`
2. Compile and run it:

   ```bash
   ghc MultiplyByFive.hs -o multiply
   ./multiply
   ```

---

### 🔍 Expected Output:

```
10
50
-15
```

