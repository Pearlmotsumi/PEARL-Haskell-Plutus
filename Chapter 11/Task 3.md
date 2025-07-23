HC11T3: Double a Number

1. Asks the user for a number
2. Reads the input
3. Multiplies it by 2
4. Prints the result

```haskell
-- DoubleNumber.hs

main :: IO ()
main = do
  putStrLn "Enter a number:"
  input <- getLine
  let number = read input :: Int
  let result = number * 2
  putStrLn ("The number multiplied by 2 is: " ++ show result)
```

### How to Run

1. Save it as `DoubleNumber.hs`
2. Open terminal and navigate to its folder
3. Run with GHCi:

```bash
ghci DoubleNumber.hs
*Main> main
```

Or compile and run:

```bash
ghc DoubleNumber.hs -o doublenumber
./doublenumber
```

### Notes:

* `read input :: Int` converts the input string to an integer
* `show result` converts the integer back to a string for printing

