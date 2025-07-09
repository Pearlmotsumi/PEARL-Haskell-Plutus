 HC6T4

```haskell
-- Define productList using foldl
productList :: Num a => [a] -> a
productList = foldl (*) 1

-- Main function to test productList
main :: IO ()
main = do
    print $ productList [1, 2, 3, 4, 5]  -- 120
    print $ productList [10, -5, 2]      -- -100
    print $ productList []               -- 1 (product of empty list)
```

---

### How to run

1. Save the code in a file, e.g., `ProductList.hs`
2. Compile and run:

```bash
ghc ProductList.hs -o productlist
./productlist
```

---

### Expected output

```
120
-100
1
```

