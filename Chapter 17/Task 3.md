HC17T3: Monoid Instance for Severity

---

### ✅ Haskell Code: `Severity` with `Semigroup` and `Monoid` Instances

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

-- Main to demonstrate
main :: IO ()
main = do
  let sev1 = Low
      sev2 = High
      sev3 = Medium

  putStrLn $ "Low <> High = " ++ show (sev1 <> sev2)
  putStrLn $ "Medium <> Low = " ++ show (sev3 <> sev1)
  putStrLn $ "mempty <> High = " ++ show (mempty <> sev2)
  putStrLn $ "High <> mempty = " ++ show (sev2 <> mempty)
```

---

### 🧪 Example Output

```
Low <> High = High
Medium <> Low = Medium
mempty <> High = High
High <> mempty = High
```

---

### 🔍 Explanation

* `mempty = Low` means combining with `Low` does not increase severity.
* `mappend = (<>)` uses the `Semigroup` combination (`max`).


