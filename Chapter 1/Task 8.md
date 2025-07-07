HC1T8 - Task 8: Higher-Order Functions

```haskell
-- Define applyTwice: applies a function twice to an input
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

-- Example function: increment a number by 1
increment :: Int -> Int
increment x = x + 1

-- Main function to test applyTwice
main :: IO ()
main = do
    let result = applyTwice increment 10  -- increment (increment 10) = increment 11 = 12
    putStrLn "Applying increment function twice to 10:"
    print result
```

### Expected Output:

```
Applying increment function twice to 10:
12
```

### How to Run:

1. Save the code in a file named `ApplyTwice.hs`
2. Open a terminal and compile:

   ```bash
   ghc ApplyTwice.hs -o applyTwice
   ./applyTwice
   ```

