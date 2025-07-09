HC6T9

---

### ✅ Haskell Code:

```haskell
-- Recursive implementation of map
myMap :: (a -> b) -> [a] -> [b]
myMap _ []     = []
myMap f (x:xs) = f x : myMap f xs

-- Example function to use with myMap
square :: Int -> Int
square x = x * x

-- Main function to test myMap
main :: IO ()
main = do
    print $ myMap square [1, 2, 3, 4, 5]   -- [1,4,9,16,25]
    print $ myMap (+1) [10, 20, 30]       -- [11,21,31]
    print $ myMap show [1, 2, 3]          -- ["1","2","3"]
```

---

### 🛠 How to Run:

1. Save the file as `MyMap.hs`
2. Compile and run:

```bash
ghc MyMap.hs -o mymap
./mymap
```

---

### 🔍 Expected Output:

```
[1,4,9,16,25]
[11,21,31]
["1","2","3"]
```


