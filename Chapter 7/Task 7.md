HC7T7: Implement a function using Bounded and Enum

```haskell
-- Define the Color data type
data Color = Red | Green | Blue deriving (Show, Eq)

-- Define nextColor function with wrap-around
nextColor :: Color -> Color
nextColor Red   = Green
nextColor Green = Blue
nextColor Blue  = Red

-- Main function to test nextColor
main :: IO ()
main = do
    print $ nextColor Red    -- Green
    print $ nextColor Green  -- Blue
    print $ nextColor Blue   -- Red
```

---

### How to run

1. Save as `NextColor.hs`
2. Compile and run:

```bash
ghc NextColor.hs -o nextcolor
./nextcolor
```

---

### Expected output

```
Green
Blue
Red
```

