HC5T2: Filtering Odd Numbers

---

### ✅ Haskell Code:

```haskell
-- Define a function that filters odd numbers from a list
extractOdds :: [Int] -> [Int]
extractOdds xs = filter odd xs

-- Main function to run and display the result
main :: IO ()
main = do
    let numbers = [1..30]
    let oddNumbers = extractOdds numbers
    putStrLn $ "Original list: " ++ show numbers
    putStrLn $ "Odd numbers:    " ++ show oddNumbers
```

---

### 🛠 How to Run

1. Save the code in a file, e.g., `ExtractOdds.hs`
2. Compile and run it:

   ```bash
   ghc ExtractOdds.hs -o extractodds
   ./extractodds
   ```

---

### 🔍 Expected Output:

```
Original list: [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30]
Odd numbers:    [1,3,5,7,9,11,13,15,17,19,21,23,25,27,29]
```


