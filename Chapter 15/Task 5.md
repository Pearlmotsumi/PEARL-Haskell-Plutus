HC15T5: Safe Division Using Maybe

---

### ✅ Haskell Code (Safe Division with `Maybe`)

```haskell
-- Define a safe division function
safeDiv :: Int -> Int -> Maybe Int
safeDiv _ 0 = Nothing            -- Division by zero returns Nothing
safeDiv x y = Just (x `div` y)   -- Otherwise return the result wrapped in Just

-- Main function demonstrating usage
main :: IO ()
main = do
  putStrLn "Enter numerator:"
  numInput <- getLine
  putStrLn "Enter denominator:"
  denomInput <- getLine
  let numerator = read numInput :: Int
      denominator = read denomInput :: Int
  case safeDiv numerator denominator of
    Nothing   -> putStrLn "Error: Cannot divide by zero!"
    Just res  -> putStrLn $ "Result: " ++ show res
```

---

### 🔍 How It Works

* `safeDiv` returns `Nothing` if the denominator is `0`.
* In `main`, user input is read and parsed, then passed to `safeDiv`.
* A `case` expression is used to pattern-match on the `Maybe Int` result.

---

### 🧪 Example Run

**Input:**

```
Enter numerator:
10
Enter denominator:
2
```

**Output:**

```
Result: 5
```

**Input:**

```
Enter denominator:
0
```

**Output:**

```
Error: Cannot divide by zero!
```

---
