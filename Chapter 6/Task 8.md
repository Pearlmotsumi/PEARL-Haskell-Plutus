HC6T8

---

### ✅ Haskell Code:

```haskell
-- Function to filter even numbers from a list
filterEvens :: [Int] -> [Int]
filterEvens = filter even

-- Main function to test filterEvens
main :: IO ()
main = do
    print $ filterEvens [1, 2, 3, 4, 5, 6]   -- [2,4,6]
    print $ filterEvens [11, 13, 15]        -- []
    print $ filterEvens [2, 4, 6, 8]         -- [2,4,6,8]
    print $ filterEvens []                  -- []
```

---

### 🛠 How to Run:

1. Save the code in a file, e.g., `FilterEvens.hs`
2. Compile and run:

```bash
ghc FilterEvens.hs -o filterevens
./filterevens
```

---

### 🔍 Expected Output:

```
[2,4,6]
[]
[2,4,6,8]
[]
```


