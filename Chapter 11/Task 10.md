HC11T10: Reverse User Input

1. Reads a line of input from the user
2. Reverses the string
3. Prints the reversed result

```haskell
-- ReverseString.hs

main :: IO ()
main = do
  putStrLn "Enter a string to reverse:"
  input <- getLine
  let reversed = reverse input
  putStrLn ("Reversed string: " ++ reversed)
```

---

### How to Run

1. Save this code in a file named `ReverseString.hs`
2. Run it in GHCi:

```bash
ghci ReverseString.hs
*Main> main
```

Or compile and run:

```bash
ghc ReverseString.hs -o reversestring
./reversestring
```

---

### Example Interaction

```
Enter a string to reverse:
Haskell
Reversed string: lleksaH
```


