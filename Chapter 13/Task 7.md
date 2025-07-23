HC13T7: Use Custom Module in Main

1. **Defines a custom module** `SumNonEmpty` with a `sumNonEmpty` function
2. **Imports the module** in `Main.hs`
3. **Calculates the sum** of a non-empty list of numbers and prints it

---

### ✅ Step 1: `SumNonEmpty.hs`

```haskell
-- SumNonEmpty.hs

module SumNonEmpty (sumNonEmpty) where

-- Private helper (not exported)
emptyListError :: String
emptyListError = "Error: Cannot compute the sum of an empty list."

-- Public function
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error emptyListError
sumNonEmpty xs = sum xs
```

---

### ✅ Step 2: `Main.hs`

```haskell
-- Main.hs

import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
  let numbers = [5, 10, 20, 30]
  let result = sumNonEmpty numbers
  putStrLn $ "The sum of the list is: " ++ show result
```

---

### 🛠 How to Compile and Run

1. Save both `SumNonEmpty.hs` and `Main.hs` in the **same directory**
2. Compile and run:

```bash
ghc Main.hs
./Main
```

---

### ✅ Expected Output

```
The sum of the list is: 65
```

If you try using an empty list (e.g., `let numbers = []`), it will show:

```
*** Exception: Error: Cannot compute the sum of an empty list.
```

---

