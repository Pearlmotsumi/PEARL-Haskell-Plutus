HC12T8: Merge Two Sorted Lists

```haskell
-- MergeLists.hs

mergeLists :: Ord a => [a] -> [a] -> [a]
mergeLists [] ys = ys
mergeLists xs [] = xs
mergeLists (x:xs) (y:ys)
  | x <= y    = x : mergeLists xs (y:ys)
  | otherwise = y : mergeLists (x:xs) ys

main :: IO ()
main = do
  let list1 = [1,3,5,7]
      list2 = [2,4,6,8,10]
      merged = mergeLists list1 list2
  putStrLn ("Merged list: " ++ show merged)
```

---

### How to Run

1. Save the code as `MergeLists.hs`
2. Run it in GHCi:

```bash
ghci MergeLists.hs
*Main> main
```

Or compile and run:

```bash
ghc MergeLists.hs -o mergelists
./mergelists
```

---

### Output

```
Merged list: [1,2,3,4,5,6,7,8,10]
```

