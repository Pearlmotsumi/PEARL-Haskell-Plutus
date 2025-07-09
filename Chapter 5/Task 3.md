HC5T3: Checking for Uppercase Letters

---

### ✅ Haskell Code:

```haskell
import Data.Char (isUpper)

-- Function to check if any word starts with an uppercase letter
hasCapitalStart :: [String] -> Bool
hasCapitalStart wordsList = any startsWithCapital wordsList
  where
    startsWithCapital :: String -> Bool
    startsWithCapital (x:_) = isUpper x
    startsWithCapital []    = False  -- Handle empty strings safely

-- Main function to test hasCapitalStart
main :: IO ()
main = do
    let test1 = ["hello", "world", "Haskell"]
    let test2 = ["this", "is", "lowercase"]
    let test3 = ["", "Empty", "test"]
    
    putStrLn $ "Test 1: " ++ show test1 ++ " -> " ++ show (hasCapitalStart test1)
    putStrLn $ "Test 2: " ++ show test2 ++ " -> " ++ show (hasCapitalStart test2)
    putStrLn $ "Test 3: " ++ show test3 ++ " -> " ++ show (hasCapitalStart test3)
```

---

### 🛠 How to Run

1. Save the code in a file, e.g., `HasCapitalStart.hs`
2. Compile and run it:

   ```bash
   ghc HasCapitalStart.hs -o hascapital
   ./hascapital
   ```

---

### 🔍 Expected Output:

```
Test 1: ["hello","world","Haskell"] -> True
Test 2: ["this","is","lowercase"] -> False
Test 3: ["","Empty","test"] -> True
```

