HC5T8: Point-Free Style

```haskell
-- Point-free style definition of addFive
addFive :: Num a => a -> a
addFive = (+ 5)

-- Main function to test addFive
main :: IO ()
main = do
    print $ addFive 10  -- 15
    print $ addFive (-3) -- 2
    print $ addFive 0    -- 5
```

---

### How to run

1. Save as `AddFive.hs`
2. Compile and run:

```bash
ghc AddFive.hs -o addfive
./addfive
```

---

### Expected output:

```
15
2
5
```


