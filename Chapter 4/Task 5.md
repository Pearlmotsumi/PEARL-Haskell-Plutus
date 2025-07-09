HC4T5 - Task 5: Add a Catch-All Pattern with a Custom Message

---

### ✅ Modified `specialBirthday` with age in default message:

```haskell
-- Define specialBirthday using pattern matching
specialBirthday :: Int -> String
specialBirthday 1   = "First birthday!"
specialBirthday 18  = "You're an adult now!"
specialBirthday 100 = "A century old!"
specialBirthday age = "You are " ++ show age ++ " years old. Just another birthday."

-- Main function to test specialBirthday
main :: IO ()
main = do
    putStrLn $ "Age 1   -> " ++ specialBirthday 1
    putStrLn $ "Age 18  -> " ++ specialBirthday 18
    putStrLn $ "Age 100 -> " ++ specialBirthday 100
    putStrLn $ "Age 30  -> " ++ specialBirthday 30
    putStrLn $ "Age 45  -> " ++ specialBirthday 45
```

---

### 🛠 How to Run

1. Save this in a file like `SpecialBirthday.hs`
2. Compile and run it:

   ```bash
   ghc SpecialBirthday.hs -o specialbirthday
   ./specialbirthday
   ```

---

### 🎉 Expected Output

```
Age 1   -> First birthday!
Age 18  -> You're an adult now!
Age 100 -> A century old!
Age 30  -> You are 30 years old. Just another birthday.
Age 45  -> You are 45 years old. Just another birthday.
```


