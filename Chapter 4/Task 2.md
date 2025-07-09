HC4T2 - Task 2: Define a dayType Function

```haskell
-- Define the dayType function using pattern matching
dayType :: String -> String
dayType "Saturday" = "It's a weekend!"
dayType "Sunday"   = "It's a weekend!"
dayType "Monday"   = "It's a weekday."
dayType "Tuesday"  = "It's a weekday."
dayType "Wednesday"= "It's a weekday."
dayType "Thursday" = "It's a weekday."
dayType "Friday"   = "It's a weekday."
dayType _          = "Invalid day"

-- Main function to test dayType
main :: IO ()
main = do
    putStrLn $ "Monday    -> " ++ dayType "Monday"
    putStrLn $ "Saturday  -> " ++ dayType "Saturday"
    putStrLn $ "Sunday    -> " ++ dayType "Sunday"
    putStrLn $ "Holiday   -> " ++ dayType "Holiday"
```

---

### ✅ How to Run

1. Save this code in a file, e.g., `DayType.hs`
2. Compile and run it using GHC:

   ```bash
   ghc DayType.hs -o daytype
   ./daytype
   ```

---

### 🔍 Expected Output

```
Monday    -> It's a weekday.
Saturday  -> It's a weekend!
Sunday    -> It's a weekend!
Holiday   -> Invalid day
```

