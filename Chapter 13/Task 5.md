HC13T5: Restrict Module Export List

---

### ✅ Step 1: `SumNonEmpty.hs` — Export only `sumNonEmpty`

```haskell
-- SumNonEmpty.hs

module SumNonEmpty (sumNonEmpty) where

-- Private helper function, not exported
emptyListError :: String
emptyListError = "Error: Cannot compute sum of an empty list."

-- Public function (only this is exported)
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error emptyListError
sumNonEmpty xs = sum xs
```

🔒 `emptyListError` is **private** — it’s defined in the module but **not exported**.

---

### ✅ Step 2: `Main.hs` — Import and use `sumNonEmpty`

```haskell
-- Main.hs

import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
  let list1 = [10, 20, 30]
      list2 = []  -- This will cause an error if used
  putStrLn $ "Sum of list1: " ++ show (sumNonEmpty list1)

  -- Uncomment the next line to test the error on empty list
  -- putStrLn $ "Sum of list2: " ++ show (sumNonEmpty list2)
```

---

### 🛠 How to Run

1. Save both files in the same directory
2. Compile and run:

```bash
ghc Main.hs
./Main
```

---

### ✅ Output

```
Sum of list1: 60
```

If you uncomment the line for `list2`, you'll get:

```
*** Exception: Error: Cannot compute sum of an empty list.
```

---


