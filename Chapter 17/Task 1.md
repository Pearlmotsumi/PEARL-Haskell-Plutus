HC17T1: Severity Data Type and Semigroup Instance

* Defines a `Severity` data type with four levels: `Low`, `Medium`, `High`, and `Critical`.
* Implements a `Semigroup` instance where combining two severities returns the higher (more severe) one.
* Demonstrates the usage in `main`.

---

### ✅ Haskell Code: Severity Type with Semigroup Instance

```haskell
import Data.Semigroup (Semigroup(..))

-- Define Severity data type
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord, Enum, Bounded)

-- Semigroup instance where higher severity wins
instance Semigroup Severity where
  s1 <> s2 = max s1 s2

-- Main to demonstrate combining severities
main :: IO ()
main = do
  let sev1 = Low
      sev2 = High
      sev3 = Medium
      sev4 = Critical

  putStrLn $ "Low <> High = " ++ show (sev1 <> sev2)
  putStrLn $ "Medium <> Low = " ++ show (sev3 <> sev1)
  putStrLn $ "High <> Critical = " ++ show (sev2 <> sev4)
  putStrLn $ "Critical <> Medium = " ++ show (sev4 <> sev3)
```

---

### 🧪 Example Output

```
Low <> High = High
Medium <> Low = Medium
High <> Critical = Critical
Critical <> Medium = Critical
```

---

### 🔍 Explanation

* The deriving of `Ord` allows using `max` to get the higher severity.
* The `Semigroup` instance uses `max` to combine severities.

