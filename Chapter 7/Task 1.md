HC7T1: Implement an Eq instance for a custom data type

```haskell
-- Define the Color data type
data Color = Red | Green | Blue

-- Implement Eq type class for Color
instance Eq Color where
    Red   == Red   = True
    Green == Green = True
    Blue  == Blue  = True
    _     == _     = False

-- Main function to test Color equality
main :: IO ()
main = do
    print $ Red == Red       -- True
    print $ Red == Green     -- False
    print $ Blue == Blue     -- True
    print $ Green == Blue    -- False
```

---

### How to run

1. Save the code in a file, e.g., `ColorEq.hs`
2. Compile and run:

```bash
ghc ColorEq.hs -o coloreq
./coloreq
```

---

### Expected output

```
True
False
True
False
```

