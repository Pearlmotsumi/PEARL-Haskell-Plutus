HC7T9: Define a type class with multiple instances

```haskell
-- Define Shape data type
data Shape = Circle Double | Rectangle Double Double

-- Type class Describable
class Describable a where
    describe :: a -> String

-- Implement Describable for Bool
instance Describable Bool where
    describe True  = "This is True"
    describe False = "This is False"

-- Implement Describable for Shape
instance Describable Shape where
    describe (Circle r)    = "A circle with radius " ++ show r
    describe (Rectangle w h) = "A rectangle with width " ++ show w ++ " and height " ++ show h

-- Main function to test describe
main :: IO ()
main = do
    putStrLn $ describe True
    putStrLn $ describe False
    putStrLn $ describe (Circle 5.0)
    putStrLn $ describe (Rectangle 3.0 4.0)
```

---

### How to run

1. Save as `DescribableExample.hs`
2. Compile and run:

```bash
ghc DescribableExample.hs -o describable
./describable
```

---

### Expected output

```
This is True
This is False
A circle with radius 5.0
A rectangle with width 3.0 and height 4.0
```


