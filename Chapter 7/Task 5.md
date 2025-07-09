HC7T5: Implement a function that uses Num constraints

```haskell
-- Define squareArea with a Num typeclass constraint
squareArea :: Num a => a -> a
squareArea side = side * side

-- Main function to test squareArea
main :: IO ()
main = do
    print $ squareArea (5 :: Int)        -- 25
    print $ squareArea (3.5 :: Float)    -- 12.25
    print $ squareArea (2.2 :: Double)   -- 4.84
```

---

### How to run

1. Save as `SquareArea.hs`
2. Compile and run:

```bash
ghc SquareArea.hs -o squarearea
./squarearea
```

---

### Expected output

```
25
12.25
4.84
```


