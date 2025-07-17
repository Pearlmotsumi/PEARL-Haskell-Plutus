HC10T1: ShowSimple Type Class

1. Defines a `PaymentMethod` data type.
2. Defines a custom type class `ShowSimple`.
3. Implements the `ShowSimple` type class for `PaymentMethod`.
4. Demonstrates the use of `showSimple` in `main`.

---

### ✅ Haskell Code

```haskell
-- Define the PaymentMethod data type
data PaymentMethod = Cash | Card | Cryptocurrency

-- Define a new type class ShowSimple
class ShowSimple a where
  showSimple :: a -> String

-- Implement ShowSimple for PaymentMethod
instance ShowSimple PaymentMethod where
  showSimple Cash          = "Paid with Cash"
  showSimple Card          = "Paid with Card"
  showSimple Cryptocurrency = "Paid with Cryptocurrency"

-- Main function to demonstrate usage
main :: IO ()
main = do
  let method1 = Cash
      method2 = Card
      method3 = Cryptocurrency
  putStrLn $ showSimple method1
  putStrLn $ showSimple method2
  putStrLn $ showSimple method3
```

---

### 🟢 Sample Output

```
Paid with Cash
Paid with Card
Paid with Cryptocurrency
```
