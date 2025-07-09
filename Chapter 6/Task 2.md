HC6T2

```haskell
-- Recursive Fibonacci function
fibonacci :: Integer -> Integer
fibonacci 0 = 0
fibonacci 1 = 1
fibonacci n
    | n > 1     = fibonacci (n - 1) + fibonacci (n - 2)
    | otherwise = error "Fibonacci is not defined for negative numbers"

-- Main function to test fibonacci
main :: IO ()
main = do
    print $ fibonacci 0   -- 0
    print $ fibonacci 1   -- 1
    print $ fibonacci 5   -- 5
    print $ fibonacci 10  -- 55
```

---

### How to run

1. Save the code in a file, e.g., `Fibonacci.hs`
2. Compile and run it:

```bash
ghc Fibonacci.hs -o fibonacci
./fibonacci
```

---

### Expected output

```
0
1
5
55
```

