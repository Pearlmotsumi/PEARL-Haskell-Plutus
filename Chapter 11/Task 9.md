HC11T9: Sum Two Numbers

1. Reads two numbers from the user
2. Calculates their sum
3. Prints the result

```haskell
-- SumTwoNumbers.hs

main :: IO ()
main = do
  putStrLn "Enter the first number:"
  input1 <- getLine
  putStrLn "Enter the second number:"
  input2 <- getLine
  let num1 = read input1 :: Int
      num2 = read input2 :: Int
      sumResult = num1 + num2
  putStrLn ("The sum is: " ++ show sumResult)
```

---

### How to Run

1. Save it as `SumTwoNumbers.hs`
2. Run it in GHCi:

```bash
ghci SumTwoNumbers.hs
*Main> main
```

Or compile and run:

```bash
ghc SumTwoNumbers.hs -o sumtwo
./sumtwo
```

---

### Example Interaction

```
Enter the first number:
8
Enter the second number:
5
The sum is: 13
```

