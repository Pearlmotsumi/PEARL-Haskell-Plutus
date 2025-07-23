HC11T1: Greet the User

```haskell
-- Greeting.hs

main :: IO ()
main = do
  putStrLn "What is your name?"
  name <- getLine
  putStrLn ("Hello, " ++ name ++ "! Nice to meet you.")
```

### How to Run

1. Save this code in a file called `Greeting.hs`
2. Open your terminal and navigate to the file's directory
3. Run it using GHCi:

```bash
ghci Greeting.hs
*Main> main
```

Or compile it with:

```bash
ghc Greeting.hs -o greeting
./greeting
```


