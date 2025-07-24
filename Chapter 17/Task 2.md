HC17T2: Min and Max Newtypes with Semigroup

---

### ✅ Haskell Code: `Min` and `Max` Newtypes with Semigroup Instances

```haskell
{-# LANGUAGE GeneralizedNewtypeDeriving #-}

import Data.Semigroup (Semigroup(..))
import Data.Monoid (Monoid(..))

-- Min newtype wrapper
newtype Min a = Min { getMin :: a }
  deriving (Show, Eq, Ord)

instance Ord a => Semigroup (Min a) where
  Min x <> Min y = Min (min x y)

instance Ord a => Monoid (Min a) where
  mempty = Min maxBound

-- Max newtype wrapper
newtype Max a = Max { getMax :: a }
  deriving (Show, Eq, Ord)

instance Ord a => Semigroup (Max a) where
  Max x <> Max y = Max (max x y)

instance (Bounded a, Ord a) => Monoid (Max a) where
  mempty = Max minBound

-- Main function to demonstrate Min and Max
main :: IO ()
main = do
  let mins = [Min 10, Min 3, Min 7]
      maxs = [Max 10, Max 3, Max 7]

  putStrLn $ "Minimum of [10,3,7]: " ++ show (getMin $ foldr (<>) mempty mins)
  putStrLn $ "Maximum of [10,3,7]: " ++ show (getMax $ foldr (<>) mempty maxs)
```

---

### 🧪 Example Output

```
Minimum of [10,3,7]: 3
Maximum of [10,3,7]: 10
```

---

### 🔍 Notes

* `mempty` for `Min` is set to `maxBound` (so folding finds the actual minimum).
* `mempty` for `Max` is set to `minBound` (so folding finds the actual maximum).
* `Bounded` constraint is needed for `mempty` in `Monoid` instance of `Max`.
* `GeneralizedNewtypeDeriving` helps derive standard instances like `Ord`, `Eq`.


