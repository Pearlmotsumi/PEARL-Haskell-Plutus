HC1T6 - Task 6: Using Type Signatures

```haskell
-- Define the function to add two numbers
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

-- Main function to test it
main :: IO ()
main = do
    let a = 7
    let b = 5
    let result = addNumbers a b
    putStrLn ("The sum of " ++ show a ++ " and " ++ show b ++ " is: " ++ show result)
```

### Expected Output:

```
The sum of 7 and 5 is: 12
```

### How to Run:

1. Save the file as `AddNumbers.hs`
2. Compile and run:

   ```bash
   ghc AddNumbers.hs -o addNumbers
   ./addNumbers
   ```


