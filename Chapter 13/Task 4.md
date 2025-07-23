HC13T4: SumNonEmpty Module

* A **module named** `SumNonEmpty` defining the `sumNonEmpty` function
* The function throws an **error** if called on an **empty list**
* A `Main` module that **demonstrates its usage**

---

### ✅ Step 1: `SumNonEmpty.hs` — the module

```haskell
-- SumNonEmpty.hs

module SumNonEmpty (sumNonEmpty) where

-- Sum function that throws an error on empty list
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error "Error: Cannot compute sum of an empty list."
sumNonEmpty xs = sum xs
```

---

### ✅ Step 2: `Main.hs` — main program using the module

```haskell
-- Main.hs

import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
  let list1 = [1, 2, 3, 4]
  let list2 = []  -- This will trigger an error

  putStrLn $ "Sum of list1: " ++ show (sumNonEmpty list1)

  -- Uncomment the line below to see the error when applied to an empty list
  -- putStrLn $ "Sum of list2: " ++ show (sumNonEmpty list2)
```

---

### 🛠 How to Run

1. Save both files in the same directory: `SumNonEmpty.hs` and `Main.hs`
2. Compile and run:

```bash
ghc Main.hs
./Main
```

---

### ✅ Sample Output

```
Sum of list1: 10
```

If you uncomment the `list2` line, you’ll get:

```
*** Exception: Error: Cannot compute sum of an empty list.
```

---

