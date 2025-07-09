HC5T9: Higher-Order Function to Transform a List

```haskell
-- transformList applies a function twice to every element in the list
transformList :: (a -> a) -> [a] -> [a]
transformList f = map (f . f)

-- Example function to use with transformList
increment :: Int -> Int
increment x = x + 1

-- Main function to test transformList
main :: IO ()
main = do
    let nums = [1, 2, 3, 4]
    putStrLn $ "Original list: " ++ show nums
    putStrLn $ "After applying increment twice: " ++ show (transformList increment nums)
```

---

### How to run

1. Save as `TransformList.hs`
2. Compile and run:

```bash
ghc TransformList.hs -o transformlist
./transformlist
```

---

### Expected output

```
Original list: [1,2,3,4]
After applying increment twice: [3,4,5,6]
```


