HC11T5: Repeat Until "quit"


```haskell
-- RepeatUntilQuit.hs

main :: IO ()
main = do
  putStrLn "Type something (or type 'quit' to exit):"
  loop

loop :: IO ()
loop = do
  input <- getLine
  if input == "quit"
    then putStrLn "Goodbye!"
    else do
      putStrLn ("You entered: " ++ input)
      loop
```

### How to Run

1. Save the code in a file called `RepeatUntilQuit.hs`
2. Run it in GHCi:

```bash
ghci RepeatUntilQuit.hs
*Main> main
```

Or compile and run:

```bash
ghc RepeatUntilQuit.hs -o repeat
./repeat
```

### Example interaction:

```
Type something (or type 'quit' to exit):
hello
You entered: hello
how are you
You entered: how are you
quit
Goodbye!
```

