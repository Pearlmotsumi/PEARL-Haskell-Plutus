HC5T6: Function Composition

1. **Squares each number** in a list.
2. **Filters the results** to keep only the **even** squares.

---

### ✅ Haskell Code (using function composition):

```haskell
-- Define the composed function: square the numbers, then filter even ones
evenSquares :: [Int] -> [Int]
evenSquares = filter even . map (^2)

-- Main function to test evenSquares
main :: IO ()
main = do
    let numbers = [1..10]
    putStrLn $ "Original list: " ++ show numbers
    putStrLn $ "Even squares:   " ++ show (evenSquares numbers)
```

---

### 🛠 How to Run:

1. Save this code in a file, e.g., `EvenSquares.hs`
2. Compile and run:

   ```bash
   ghc EvenSquares.hs -o evensquares
   ./evensquares
   ```

---

### 🔍 Expected Output:

```
Original list: [1,2,3,4,5,6,7,8,9,10]
Even squares:   [4,16,36,64,100]
```

