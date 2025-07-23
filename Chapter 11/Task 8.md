HC11T8: Even or Odd Checker

1. Reads a number from the user
2. Checks if it is even or odd
3. Prints the result

```haskell
-- EvenOrOdd.hs

main :: IO ()
main = do
  putStrLn "Enter a number:"
  input <- getLine
  let number = read input :: Int
  if even number
    then putStrLn "The number is even."
    else putStrLn "The number is odd."
```

---

### How to Run

1. Save the code in a file called `EvenOrOdd.hs`
2. Run it in GHCi:

```bash
ghci EvenOrOdd.hs
*Main> main
```

Or compile and run:

```bash
ghc EvenOrOdd.hs -o evenorodd
./evenorodd
```

---

### Example Interaction

```
Enter a number:
7
The number is odd.
```

