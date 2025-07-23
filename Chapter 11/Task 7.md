HC11T7: User Options

* Prints a list of options to the user
* Reads the user's choice
* Executes different code based on the selected option

```haskell
-- MenuOptions.hs

main :: IO ()
main = do
  putStrLn "Choose an option:"
  putStrLn "1. Greet"
  putStrLn "2. Add two numbers"
  putStrLn "3. Say goodbye"
  putStrLn "Enter your choice (1-3):"
  choice <- getLine
  case choice of
    "1" -> do
      putStrLn "What is your name?"
      name <- getLine
      putStrLn ("Hello, " ++ name ++ "!")
    "2" -> do
      putStrLn "Enter the first number:"
      num1 <- getLine
      putStrLn "Enter the second number:"
      num2 <- getLine
      let a = read num1 :: Int
          b = read num2 :: Int
      putStrLn ("The sum is: " ++ show (a + b))
    "3" -> putStrLn "Goodbye!"
    _   -> putStrLn "Invalid option. Please run the program again."
```

---

### How to Run

1. Save it as `MenuOptions.hs`
2. Run it in GHCi:

```bash
ghci MenuOptions.hs
*Main> main
```

Or compile and run:

```bash
ghc MenuOptions.hs -o menu
./menu
```

---

### Sample Interaction

```
Choose an option:
1. Greet
2. Add two numbers
3. Say goodbye
Enter your choice (1-3):
1
What is your name?
Alice
Hello, Alice!
```


