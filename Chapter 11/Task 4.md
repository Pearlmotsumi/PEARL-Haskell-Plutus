HC11T4: Concatenate Two Lines

```haskell
-- ConcatenateLines.hs

main :: IO ()
main = do
  putStrLn "Enter the first line:"
  line1 <- getLine
  putStrLn "Enter the second line:"
  line2 <- getLine
  let combined = line1 ++ line2
  putStrLn ("Concatenated result: " ++ combined)
```

### How to Run

1. Save the file as `ConcatenateLines.hs`
2. Open terminal and go to the directory where it's saved
3. Run it using GHCi:

```bash
ghci ConcatenateLines.hs
*Main> main
```

Or compile and run:

```bash
ghc ConcatenateLines.hs -o concatlines
./concatlines
```

### Example interaction:

```
Enter the first line:
Hello
Enter the second line:
World
Concatenated result: HelloWorld
```

