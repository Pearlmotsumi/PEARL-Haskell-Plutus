HC6T10

```haskell
-- Recursive function to get digits of a number
digits :: Integer -> [Integer]
digits n
  | n < 10    = [n]
  | otherwise = digits (n `div` 10) ++ [n `mod` 10]

-- Main function to test digits
main :: IO ()
main = do
    print $ digits 0          -- [0]
    print $ digits 12345      -- [1,2,3,4,5]
    print $ digits 987654321  -- [9,8,7,6,5,4,3,2,1]
```

---

### How to run

1. Save as `Digits.hs`
2. Compile and run:

```bash
ghc Digits.hs -o digits
./digits
```

---

### Expected output

```
[0]
[1,2,3,4,5]
[9,8,7,6,5,4,3,2,1]
```


