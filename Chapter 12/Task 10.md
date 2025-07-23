HC12T10: Mathematical Operations Module

* Defines a **module** called `MathOperations` with some basic math functions
* Uses this module in a `Main` file to demonstrate those functions

---

### 📁 Step-by-step Structure

You'll need **two files**:

---

### ✅ 1. `MathOperations.hs` — The module

```haskell
-- MathOperations.hs

module MathOperations (
  add,
  subtract',
  multiply,
  divide
) where

add :: Num a => a -> a -> a
add x y = x + y

subtract' :: Num a => a -> a -> a
subtract' x y = x - y

multiply :: Num a => a -> a -> a
multiply x y = x * y

divide :: Fractional a => a -> a -> a
divide x y = x / y
```

> Note: `subtract` is a built-in function, so we renamed it to `subtract'`.

---

### ✅ 2. `Main.hs` — The main program that uses the module

```haskell
-- Main.hs

import MathOperations

main :: IO ()
main = do
  let a = 10
      b = 5

  putStrLn $ "a = " ++ show a ++ ", b = " ++ show b
  putStrLn $ "Addition: " ++ show (add a b)
  putStrLn $ "Subtraction: " ++ show (subtract' a b)
  putStrLn $ "Multiplication: " ++ show (multiply a b)
  putStrLn $ "Division: " ++ show (divide (fromIntegral a) (fromIntegral b))
```

---

### 🔧 How to Compile and Run

Make sure both files (`MathOperations.hs` and `Main.hs`) are in the same directory.

Then compile and run like this:

```bash
ghc Main.hs
./Main
```

---

### ✅ Example Output

```
a = 10, b = 5
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
```

---


