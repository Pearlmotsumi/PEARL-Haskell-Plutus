HC7T3: Implement a function using multiple constraints

```haskell
-- Define compareValues with constraints Eq and Ord
compareValues :: (Eq a, Ord a) => a -> a -> a
compareValues x y
    | x >= y    = x
    | otherwise = y

-- Main function to test compareValues
main :: IO ()
main = do
    print $ compareValues 10 20          -- 20
    print $ compareValues 5 5            -- 5
    print $ compareValues 'a' 'z'        -- 'z'
    print $ compareValues "apple" "pear" -- "pear"
```

---

### How to run

1. Save as `CompareValues.hs`
2. Compile and run:

```bash
ghc CompareValues.hs -o comparevalues
./comparevalues
```

---

### Expected output

```
20
5
'z'
"pear"
```


