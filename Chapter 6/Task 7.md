HC6T7

---

### ✅ Haskell Code:

```haskell
-- Recursive function to compute the length of a list
listLength :: [a] -> Int
listLength []     = 0
listLength (_:xs) = 1 + listLength xs

-- Main function to test listLength
main :: IO ()
main = do
    print $ listLength [1, 2, 3, 4, 5]     -- 5
    print $ listLength "Haskell"           -- 7
    print $ listLength ([] :: [Int])       -- 0
```

---

### 🛠 How to Run:

1. Save the file as `ListLength.hs`
2. Compile and run:

```bash
ghc ListLength.hs -o listlength
./listlength
```

---

### 🔍 Expected Output:

```
5
7
0
```


