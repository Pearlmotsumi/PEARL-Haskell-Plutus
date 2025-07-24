HC17T6: maxSeverity Function

---

### ✅ Haskell Code: `maxSeverity` Using `mconcat`

```haskell
import Data.Semigroup (Semigroup(..))
import Data.Monoid (Monoid(..))

-- Severity data type
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord, Enum, Bounded)

-- Semigroup instance: higher severity wins
instance Semigroup Severity where
  s1 <> s2 = max s1 s2

-- Monoid instance: identity is Low
instance Monoid Severity where
  mempty = Low
  mappend = (<>)

-- Function to combine list of Severity values using mconcat
maxSeverity :: [Severity] -> Severity
maxSeverity = mconcat

-- Main to demonstrate maxSeverity
main :: IO ()
main = do
  let severities = [Low, Medium, High, Medium, Critical, Low]
  putStrLn $ "Max severity in the list: " ++ show (maxSeverity severities)
```

---

### 🧪 Example Output

```
Max severity in the list: Critical
```

---

### 🔍 Explanation

* `mconcat` folds the list using the `Monoid` instance, which takes the maximum severity.
* `maxSeverity` just wraps `mconcat` for convenience.

