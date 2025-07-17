HC10T8: AdvancedEq Subclass of Eq

* Define a subclass `AdvancedEq` of the standard `Eq` type class,
* Add a method `compareEquality :: a -> a -> Bool`,
* Implement `AdvancedEq` for a custom type `Color`,
* Include a `main` function to demonstrate its usage.

---

### ✅ Haskell Code

```haskell
-- Define a data type
data Color = Red | Green | Blue
  deriving (Eq, Show)

-- Define a subclass AdvancedEq of Eq
class Eq a => AdvancedEq a where
  compareEquality :: a -> a -> Bool
  compareEquality x y = x == y  -- default implementation using Eq

-- Make Color an instance of AdvancedEq
instance AdvancedEq Color

-- Main function to test
main :: IO ()
main = do
  let c1 = Red
      c2 = Blue
      c3 = Red
  print (compareEquality c1 c2)  -- Output: False
  print (compareEquality c1 c3)  -- Output: True
```

---

### 📝 Explanation

* `AdvancedEq` inherits from `Eq`, so any instance must also be an instance of `Eq`.
* We provide a **default implementation** of `compareEquality` using `(==)` from `Eq`, which can be overridden if needed.
* The `Color` type uses `deriving Eq` to satisfy the superclass constraint.

