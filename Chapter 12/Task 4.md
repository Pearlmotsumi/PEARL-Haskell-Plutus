HC12T4: First 10 Fibonacci Numbers

```haskell
-- Fibonacci.hs

-- Recursive function to compute nth Fibonacci number
fib :: Int -> Int
fib 0 = 0
fib 1 = 1
fib n = fib (n - 1) + fib (n - 2)

main :: IO ()
main = do
  putStrLn "The first 10 Fibonacci numbers are:"
  let first10 = map fib [0..9]
  print first10
```

---

### How to Run

1. Save as `Fibonacci.hs`
2. Run in GHCi:

```bash
ghci Fibonacci.hs
*Main> main
```

Or compile and run:

```bash
ghc Fibonacci.hs -o fibonacci
./fibonacci
```

---

### Output

```
The first 10 Fibonacci numbers are:
[0,1,1,2,3,5,8,13,21,34]
```


