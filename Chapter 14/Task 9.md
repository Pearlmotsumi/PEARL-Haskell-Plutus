HC14T9: PartialTypeSignatures Extension

---

### ✅ Example: Using `PartialTypeSignatures`

```haskell
{-# LANGUAGE PartialTypeSignatures #-}

-- We don't warn about partial type signatures
{-# OPTIONS_GHC -fno-warn-partial-type-signatures #-}

-- A function that doubles a number
double :: _ -> _
double x = x * 2

main :: IO ()
main = do
    let result = double (5 :: Int)
    putStrLn $ "Double of 5 is: " ++ show result
```

---

### ✅ Explanation

* The `{-# LANGUAGE PartialTypeSignatures #-}` pragma enables partial types using `_`.
* The GHC option `-fno-warn-partial-type-signatures` silences the compiler warnings.
* `double :: _ -> _` means “let GHC infer both the argument and return types.”

---

### 🧪 Sample Output

```
Double of 5 is: 10
```

---

You can use partial type signatures when you're prototyping or if a function has a long inferred type and you only care about part of it.

