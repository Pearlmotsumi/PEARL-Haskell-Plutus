HC12T3: Factorial Function

```haskell
-- Factorial.hs

factorial :: Integer -> Integer
factorial 0 = 1
factorial n
  | n > 0     = n * factorial (n - 1)
  | otherwise = error "Factorial is not defined for negative numbers"

main :: IO ()
main = do
  putStrLn "Enter a positive integer:"
  input <- getLine
  let n = read input :: Integer
  if n < 0
    then putStrLn "Please enter a non-negative integer."
    else putStrLn ("The factorial of " ++ show n ++ " is " ++ show (factorial n))
```

---

### How to Run

1. Save the code as `Factorial.hs`
2. Run it in GHCi:

```bash
ghci Factorial.hs
*Main> main
```

Or compile and run:

```bash
ghc Factorial.hs -o factorial
./factorial
```

---

### Sample interaction

```
Enter a positive integer:
5
The factorial of 5 is 120
```

