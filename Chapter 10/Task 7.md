HC10T7: Convertible Type Class

* Defines a `PaymentMethod` type,
* Creates a **type class `Convertible`** with a method `convert :: a -> b`,
* Implements an instance for converting `PaymentMethod` to `String`,
* Includes a `main` function to run the code.

---

### ✅ Haskell Code

```haskell
-- Define the PaymentMethod data type
data PaymentMethod = CreditCard | PayPal | Crypto
  deriving Show

-- Define the Convertible type class
class Convertible a b where
  convert :: a -> b

-- Implement Convertible instance from PaymentMethod to String
instance Convertible PaymentMethod String where
  convert CreditCard = "Paid with Credit Card"
  convert PayPal     = "Paid via PayPal"
  convert Crypto     = "Paid using Cryptocurrency"

-- Main function to test
main :: IO ()
main = do
  let method1 = CreditCard
  let method2 = Crypto
  putStrLn (convert method1)  -- Output: Paid with Credit Card
  putStrLn (convert method2)  -- Output: Paid using Cryptocurrency
```

---

### 💡 Notes

* The type class `Convertible` is **parameterized over both input and output types**, giving flexibility for other conversions too.
* You can later define more instances like `Convertible Int String`, etc.

