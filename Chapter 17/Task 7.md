HC17T7: multiplyProducts Function

---

### ✅ Haskell Code: `Product` newtype with `multiplyProducts`

```haskell
-- Define the Product newtype
newtype Product = Product { getProduct :: Integer }
  deriving (Show, Eq)

-- Semigroup instance: multiplication
instance Semigroup Product where
  Product x <> Product y = Product (x * y)

-- Monoid instance: identity is 1
instance Monoid Product where
  mempty = Product 1
  mappend = (<>)

-- Function to multiply a list of Products using mconcat
multiplyProducts :: [Product] -> Product
multiplyProducts = mconcat

-- Main function to demonstrate multiplyProducts
main :: IO ()
main = do
  let products = [Product 2, Product 3, Product 5]
      combined = multiplyProducts products
  putStrLn $ "Product of [2, 3, 5] = " ++ show (getProduct combined)
```

---

### 🧪 Example Output

```
Product of [2, 3, 5] = 30
```

---

### 🔍 Explanation

* `Semigroup` combines `Product` values by multiplying their contained integers.
* `Monoid` uses `Product 1` as the identity element.
* `multiplyProducts` folds a list with `mconcat` (using the monoid).


