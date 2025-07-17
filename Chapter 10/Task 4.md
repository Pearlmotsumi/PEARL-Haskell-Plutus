HC10T4: Eq Instance for Box

1. Define a **parameterized type** `Box a` with constructors `Empty` and `Has a`.
2. Make `Box a` an **instance of the `Eq` type class**, so two boxes are equal if:

   * Both are `Empty`, or
   * Both are `Has` with equal contents.

---

### ✅ Haskell Code

```haskell
-- Define a parameterized data type Box a
data Box a = Empty | Has a deriving Show

-- Make Box an instance of Eq
instance (Eq a) => Eq (Box a) where
  Empty == Empty = True
  Has x == Has y = x == y
  _ == _ = False

-- Main function to test equality
main :: IO ()
main = do
  let box1 = Has 5
  let box2 = Has 5
  let box3 = Has 10
  let box4 = Empty

  print (box1 == box2)  -- True
  print (box1 == box3)  -- False
  print (box1 == box4)  -- False
  print (box4 == Empty) -- True
```

---

### 🟢 Sample Output

```
True
False
False
True
```

### 🔎 Notes

* The `(Eq a) => Eq (Box a)` instance ensures that we can only compare `Box a` for equality if `a` itself supports equality.
* You can use this for `Box Int`, `Box String`, etc.

