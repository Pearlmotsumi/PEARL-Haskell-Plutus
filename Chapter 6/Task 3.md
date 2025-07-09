HC6T3

```haskell
-- Define sumList using foldr
sumList :: Num a => [a] -> a
sumList = foldr (+) 0

-- Main function to test sumList
main :: IO ()
main = do
    print $ sumList [1, 2, 3, 4, 5]  -- 15
    print $ sumList [10, -5, 7]      -- 12
    print $ sumList []               -- 0
```

---

### How to run

1. Save as `SumList.hs`
2. Compile and run:

```bash
ghc SumList.hs -o sumlist
./sumlist
```

---

### Expected output

```
15
12
0
```

