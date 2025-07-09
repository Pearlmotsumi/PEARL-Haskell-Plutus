HC6T5

```haskell
-- Recursive function to reverse a list
reverseList :: [a] -> [a]
reverseList []     = []
reverseList (x:xs) = reverseList xs ++ [x]

-- Main function to test reverseList
main :: IO ()
main = do
    print $ reverseList [1, 2, 3, 4, 5]      -- [5,4,3,2,1]
    print $ reverseList "Haskell"             -- "lleksaH"
    print $ reverseList ([] :: [Int])         -- []
```

---

### How to run

1. Save this code in a file, e.g., `ReverseList.hs`
2. Compile and run:

```bash
ghc ReverseList.hs -o reverselist
./reverselist
```

---

### Expected output

```
[5,4,3,2,1]
"lleksaH"
[]
```
