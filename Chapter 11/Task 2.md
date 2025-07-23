HC11T2: Count Characters in a Line

```haskell
-- CountCharacters.hs

main :: IO ()
main = do
  putStrLn "Enter a line of text:"
  line <- getLine
  let count = length line
  putStrLn ("The number of characters is: " ++ show count)
```

### How to Run

1. Save the code in a file called `CountCharacters.hs`
2. Open a terminal and navigate to the file's directory
3. Run it in GHCi:

```bash
ghci CountCharacters.hs
*Main> main
```

Or compile and run:

```bash
ghc CountCharacters.hs -o countchars
./countchars
```

This program uses:

* `getLine` to read input
* `length` to count characters
* `show` to convert the number to a string for printing


