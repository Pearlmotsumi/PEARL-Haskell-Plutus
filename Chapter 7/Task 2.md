HC7T2: Implement an Ord instance for a custom data type

```haskell
-- Define the Color data type
data Color = Red | Green | Blue deriving (Eq, Show)

-- Implement Ord type class for Color with Red < Green < Blue
instance Ord Color where
    compare Red   Red   = EQ
    compare Red   _     = LT
    compare Green Red   = GT
    compare Green Green = EQ
    compare Green Blue  = LT
    compare Blue  Blue  = EQ
    compare Blue  _     = GT

-- Main function to test Ord implementation
main :: IO ()
main = do
    print $ Red < Green     -- True
    print $ Green < Blue    -- True
    print $ Blue > Red      -- True
    print $ Green > Green   -- False
    print $ Red == Red      -- True
    print $ Blue <= Blue    -- True
```

---

### How to run

1. Save the code as `ColorOrd.hs`
2. Compile and run:

```bash
ghc ColorOrd.hs -o colorord
./colorord
```

---

### Expected output

```
True
True
True
False
True
True
```


