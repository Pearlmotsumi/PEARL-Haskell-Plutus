HC17T5: combineLists Function

---

### ✅ Haskell Code: `combineLists` Using Semigroup Instance for Lists

```haskell
import Data.Semigroup (Semigroup(..))

-- Function that combines two lists using Semigroup (<>)
combineLists :: [Int] -> [Int] -> [Int]
combineLists xs ys = xs <> ys

-- Main function to demonstrate combineLists
main :: IO ()
main = do
    let list1 = [1, 2, 3]
        list2 = [4, 5, 6]
        combined = combineLists list1 list2
    putStrLn $ "Combined list: " ++ show combined
```

---

### 🧪 Example Output

```
Combined list: [1,2,3,4,5,6]
```

---

### 🔍 Notes

* Lists in Haskell have a built-in `Semigroup` instance where `(<>)` is list concatenation.
* This function simply uses that to join two lists.

