HC4T4 - Task 4: Rewrite specialBirthday using Pattern Matching

### Original (if-else style):

```haskell
specialBirthday :: Int -> String
specialBirthday age =
    if age == 1 then "First birthday!"
    else if age == 18 then "You're an adult now!"
    else if age == 100 then "A century old!"
    else "Just another birthday."
```

---

### ✅ Rewritten Version Using **Pattern Matching** (and includes `main`):

```haskell
-- Define specialBirthday using pattern matching
specialBirthday :: Int -> String
specialBirthday 1   = "First birthday!"
specialBirthday 18  = "You're an adult now!"
specialBirthday 100 = "A century old!"
specialBirthday _   = "Just another birthday."

-- Main function to test specialBirthday
main :: IO ()
main = do
    putStrLn $ "Age 1   -> " ++ specialBirthday 1
    putStrLn $ "Age 18  -> " ++ specialBirthday 18
    putStrLn $ "Age 100 -> " ++ specialBirthday 100
    putStrLn $ "Age 30  -> " ++ specialBirthday 30
```

---

### 🛠 How to Run:

1. Save the code to a file, e.g., `SpecialBirthday.hs`
2. Compile and run with GHC:

   ```bash
   ghc SpecialBirthday.hs -o specialbirthday
   ./specialbirthday
   ```

---

### 🎉 Expected Output:

```
Age 1   -> First birthday!
Age 18  -> You're an adult now!
Age 100 -> A century old!
Age 30  -> Just another birthday.
```

