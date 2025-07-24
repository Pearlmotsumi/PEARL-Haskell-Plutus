HC17T8: foldWithSemigroup Function

---

### ✅ Haskell Code: `foldWithSemigroup` using `foldr1`

```haskell
import Data.Semigroup (Semigroup(..))
import Data.Monoid (Sum(..))

-- Function that folds a non-empty list using Semigroup's <>
foldWithSemigroup :: Semigroup a => [a] -> a
foldWithSemigroup = foldr1 (<>)

-- Main to demonstrate foldWithSemigroup
main :: IO ()
main = do
  -- Using Sum for integers
  let nums = [Sum 1, Sum 2, Sum 3, Sum 4]
      sumResult = foldWithSemigroup nums

  -- Using strings (lists) directly
  let strings = ["Hello, ", "world", "!"]
      stringResult = foldWithSemigroup strings

  putStrLn $ "Sum of [1,2,3,4] = " ++ show (getSum sumResult)
  putStrLn $ "Concatenation of strings = " ++ stringResult
```

---

### 🧪 Example Output

```
Sum of [1,2,3,4] = 10
Concatenation of strings = Hello, world!
```

---

### 🔍 Notes:

* `foldr1` requires the list to be non-empty; otherwise, it throws an error.
* For empty lists, you might want to use `mconcat` or handle empty cases separately.
* `Semigroup` provides the `<>` operator for combining.

