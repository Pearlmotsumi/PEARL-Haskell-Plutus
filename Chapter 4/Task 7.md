HC4T7 - Task 7: Ignore Elements in a List

---

### ✅ Haskell Code:

```haskell
-- Define firstAndThird to return a tuple of the first and third elements
firstAndThird :: [a] -> Maybe (a, a)
firstAndThird (x:_:z:_) = Just (x, z)  -- First and third exist
firstAndThird _         = Nothing      -- Not enough elements

-- Main function to test firstAndThird
main :: IO ()
main = do
    printTest [10, 20, 30, 40]     -- Should return Just (10, 30)
    printTest ["a", "b", "c", "d"] -- Should return Just ("a", "c")
    printTest [1]                  -- Not enough elements
    printTest []                   -- Empty list
    printTest [5, 6]               -- Only two elements

-- Helper function to display result
printTest :: Show a => [a] -> IO ()
printTest lst = do
    putStrLn $ "Input List: " ++ show lst
    case firstAndThird lst of
        Just (a, b) -> putStrLn $ "First and third: " ++ show (a, b)
        Nothing     -> putStrLn "Not enough elements."
    putStrLn ""
```

---

### 🛠 How to Run

1. Save it as `FirstAndThird.hs`
2. Compile and run:

   ```bash
   ghc FirstAndThird.hs -o firstAndThird
   ./firstAndThird
   ```

---

### 🧾 Sample Output:

```
Input List: [10,20,30,40]
First and third: (10,30)

Input List: ["a","b","c","d"]
First and third: ("a","c")

Input List: [1]
Not enough elements.

Input List: []
Not enough elements.

Input List: [5,6]
Not enough elements.
```


