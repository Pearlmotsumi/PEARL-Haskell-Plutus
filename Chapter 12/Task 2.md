HC12T2: Add Two Numbers

```haskell
-- AddTwoNumbers.hs

addTwoNumbers :: Int -> Int -> Int
addTwoNumbers x y = x + y

main :: IO ()
main = do
  putStrLn "Enter the first number:"
  input1 <- getLine
  putStrLn "Enter the second number:"
  input2 <- getLine
  let num1 = read input1 :: Int
      num2 = read input2 :: Int
      result = addTwoNumbers num1 num2
  putStrLn ("The sum is: " ++ show result)
```

---

### How to Run

1. Save as `AddTwoNumbers.hs`
2. Run in GHCi:

```bash
ghci AddTwoNumbers.hs
*Main> main
```

Or compile and run:

```bash
ghc AddTwoNumbers.hs -o addtwonumbers
./addtwonumbers
```

---

### Sample interaction

```
Enter the first number:
4
Enter the second number:
7
The sum is: 11
```


