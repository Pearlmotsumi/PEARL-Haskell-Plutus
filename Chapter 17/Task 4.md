HC17T4: Monoid Instance for Sum Newtype

---

### ✅ Haskell Code: Custom `Sum` Newtype with `Monoid` Instance

```haskell
-- Define the Sum newtype
newtype Sum = Sum { getSum :: Int }
  deriving (Show, Eq)

-- Semigroup instance: addition
instance Semigroup Sum where
  Sum x <> Sum y = Sum (x + y)

-- Monoid instance: identity is 0
instance Monoid Sum where
  mempty = Sum 0
  mappend = (<>)

-- Main function to demonstrate Sum
main :: IO ()
main = do
  let values = [Sum 3, Sum 5, Sum 10]
      total = mconcat values
  putStrLn $ "Sum of [3,5,10] = " ++ show (getSum total)
  putStrLn $ "mempty = " ++ show (getSum (mempty :: Sum))
```

---

### 🧪 Example Output

```
Sum of [3,5,10] = 18
mempty = 0
```

---

### 🔍 Explanation

* `Semigroup` combines `Sum` values by adding their contained `Int`s.
* `Monoid` uses `Sum 0` as the identity (`mempty`).
* `mconcat` folds a list using `mappend` starting with `mempty`.


