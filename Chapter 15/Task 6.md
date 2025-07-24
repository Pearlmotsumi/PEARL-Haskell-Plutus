HC15T6: Safe Input Parsing with readMaybe

---

### ✅ Full Haskell Example Using `readMaybe`

```haskell
{-# LANGUAGE ScopedTypeVariables #-}

import Text.Read (readMaybe)

main :: IO ()
main = do
    putStrLn "Enter a number:"
    input <- getLine
    let parsed :: Maybe Int
        parsed = readMaybe input
    case parsed of
        Nothing   -> putStrLn "Invalid input: Not a valid integer."
        Just n    -> putStrLn $ "You entered the number: " ++ show n
```

---

### 🔍 Explanation

* `readMaybe` attempts to parse a `String` into a value of the desired type.
* If parsing fails, it returns `Nothing`; otherwise, it returns `Just value`.
* This avoids the crash you'd get with `read` on malformed input.

---

### 🧪 Example Run

**Input:**

```
Enter a number:
abc
```

**Output:**

```
Invalid input: Not a valid integer.
```

**Input:**

```
Enter a number:
42
```

**Output:**

```
You entered the number: 42
```

---


