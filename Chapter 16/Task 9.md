HC16T9: Remove Duplicates from List

---

### ✅ Haskell Code: Remove Duplicates from List

```haskell
import Data.List (nub)

-- Function to remove duplicates
removeDuplicates :: Eq a => [a] -> [a]
removeDuplicates = nub

-- Main function to test removeDuplicates
main :: IO ()
main = do
    putStrLn "Enter a list of values separated by spaces:"
    input <- getLine
    let items = words input
    let uniqueItems = removeDuplicates items
    putStrLn $ "List without duplicates: " ++ unwords uniqueItems
```

---

### 🧪 Example Run

```
Enter a list of values separated by spaces:
apple banana apple orange banana
List without duplicates: apple banana orange
```

---

### 🔧 Notes

* This version works for `[String]`, but you can adapt it for `[Int]` or any `Eq` type.
* `nub` comes from the `Data.List` module and removes the **first occurrence** of each duplicate.

