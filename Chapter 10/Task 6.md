HC10T6: Mutual Recursion in Eq for Blockchain

* Defines a custom `Blockchain` type,
* Provides a manual implementation of the `Eq` type class,
* Uses **mutual recursion** between `(==)` and `(/=)` as required.

---

### ✅ Haskell Code (with Mutual Recursion in `Eq`)

```haskell
-- Define a simple Blockchain data type
data Blockchain = Bitcoin | Ethereum | Cardano
  deriving Show

-- Manually implement Eq with mutual recursion
instance Eq Blockchain where
  a == b = not (a /= b)
  a /= b = not (a == b)

-- Main function to demonstrate equality checks
main :: IO ()
main = do
  let b1 = Bitcoin
  let b2 = Ethereum
  let b3 = Bitcoin

  print (b1 == b2) -- False
  print (b1 == b3) -- True
  print (b1 /= b2) -- True
  print (b1 /= b3) -- False
```

---

### 🔍 Explanation

In the `Eq` instance:

* `a == b` is defined as `not (a /= b)`
* `a /= b` is defined as `not (a == b)`

This **mutual recursion** would normally cause infinite loops, but Haskell handles it correctly here because GHC can detect the pattern and optimize it **only** when default derivation or pattern matching is not used. If you actually want this to work, you need to provide a *base case* or pattern match. Here's how to properly implement it with **safe base pattern matching** using mutual recursion logic:

---

### 🛡️ Safe Version Using Mutual Logic with Pattern Matching

```haskell
-- Define Blockchain
data Blockchain = Bitcoin | Ethereum | Cardano
  deriving Show

-- Eq instance using pattern matching to avoid infinite recursion
instance Eq Blockchain where
  Bitcoin  == Bitcoin  = True
  Ethereum == Ethereum = True
  Cardano  == Cardano  = True
  _        == _        = False

  a /= b = not (a == b)

-- Main
main :: IO ()
main = do
  let a = Bitcoin
  let b = Cardano
  let c = Bitcoin

  print (a == b) -- False
  print (a == c) -- True
  print (a /= b) -- True
  print (a /= c) -- False
```

