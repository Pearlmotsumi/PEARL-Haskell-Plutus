HC1T3 - Task 3: Checking if a Number is Greater than 18

```haskell
-- Define the function
greaterThan18 :: Int -> Bool
greaterThan18 x = x > 18

-- Main function to test it
main :: IO ()
main = do
    putStrLn "Testing greaterThan18 function:"
    print (greaterThan18 10)   -- Should print False
    print (greaterThan18 18)   -- Should print False
    print (greaterThan18 19)   -- Should print True
    print (greaterThan18 25)   -- Should print True
```

### How to Run:

1. Save the code in a file, e.g., `GreaterThan18.hs`
2. Compile and run it using GHC:

   ```bash
   ghc GreaterThan18.hs -o greaterThan18
   ./greaterThan18
   ```


