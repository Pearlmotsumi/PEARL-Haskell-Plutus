HC5T10: Combining Higher-Order Functions

```haskell
-- Define the function using filter, map, and any
anySquareGreaterThan50 :: [Int] -> Bool
anySquareGreaterThan50 xs = any (>50) $ map (^2) $ filter (>0) xs

-- Main function to test anySquareGreaterThan50
main :: IO ()
main = do
    let list1 = [1, 5, 6, 3]    -- squares: 1, 25, 36, 9 → none > 50 → False
    let list2 = [1, 8, 3, 7]    -- squares: 1, 64, 9, 49 → 64 > 50 → True
    let list3 = [-10, 0, 2]     -- filter (>0) removes -10, 0 → squares: 4 → False

    putStrLn $ "List1 has any square > 50? " ++ show (anySquareGreaterThan50 list1)
    putStrLn $ "List2 has any square > 50? " ++ show (anySquareGreaterThan50 list2)
    putStrLn $ "List3 has any square > 50? " ++ show (anySquareGreaterThan50 list3)
```

---

### How to run

1. Save as `AnySquareGreaterThan50.hs`
2. Compile and run:

```bash
ghc AnySquareGreaterThan50.hs -o anysquare
./anysquare
```

---

### Expected output

```
List1 has any square > 50? False
List2 has any square > 50? True
List3 has any square > 50? False
```


