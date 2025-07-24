HC15T8: Division with Either for Detailed Errors

---

### ✅ Full Haskell Example Using `Either` for Division

```haskell
-- Safe division using Either for detailed error handling
safeDiv :: Double -> Double -> Either String Double
safeDiv _ 0 = Left "Error: Division by zero is not allowed."
safeDiv x y = Right (x / y)

-- Main function to demonstrate safeDiv
main :: IO ()
main = do
    putStrLn "Enter numerator:"
    numStr <- getLine
    putStrLn "Enter denominator:"
    denomStr <- getLine

    let mNum = reads numStr :: [(Double, String)]
        mDenom = reads denomStr :: [(Double, String)]

    case (mNum, mDenom) of
        ([(num, "")], [(denom, "")]) ->
            case safeDiv num denom of
                Right result -> putStrLn $ "Result: " ++ show result
                Left err     -> putStrLn err
        _ -> putStrLn "Error: Invalid input. Please enter valid numbers."
```

---

### 🔍 Explanation

* **`safeDiv :: Double -> Double -> Either String Double`**

  * Returns `Right result` on success.
  * Returns `Left "error message"` if denominator is 0.

* **Input Parsing:**

  * Uses `reads` to check if input is a valid number. Ensures no leftover unparsed string.

* **`main`:**

  * Prompts for input, parses, and applies `safeDiv`.
  * Prints the result or an appropriate error message.

---

### 🧪 Example Runs

**Valid input:**

```
Enter numerator:
20
Enter denominator:
4
Result: 5.0
```

**Divide by zero:**

```
Enter numerator:
20
Enter denominator:
0
Error: Division by zero is not allowed.
```

**Invalid input:**

```
Enter numerator:
twenty
Enter denominator:
4
Error: Invalid input. Please enter valid numbers.
```

---


