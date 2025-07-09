HC7T6: Use the Integral and Floating type classes

```haskell
-- Define circleCircumference that works with Integral and Floating inputs
circleCircumference :: (Real a, Floating b) => a -> b
circleCircumference r = 2 * pi * realToFrac r

-- Main function to test circleCircumference
main :: IO ()
main = do
    print $ circleCircumference (5 :: Int)       -- Works with Integral
    print $ circleCircumference (3.5 :: Float)   -- Works with Floating
    print $ circleCircumference (2.2 :: Double)  -- Works with Floating
```

---

### How to run

1. Save as `CircleCircumference.hs`
2. Compile and run:

```bash
ghc CircleCircumference.hs -o circlecirc
./circlecirc
```

---

### Expected output

```
31.41592653589793
21.991148575128552
13.823007675238509
```

---

### Explanation

* `Real a` allows the function to accept any real numeric type (`Int`, `Integer`, `Float`, `Double`, etc.)
* `realToFrac` converts any `Real` to a more general `Fractional`/`Floating` type for calculation.
* Result type `b` is polymorphic and must be `Floating` to support `pi` and multiplication.

