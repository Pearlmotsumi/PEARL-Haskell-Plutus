HC7T10: Use a function with multiple type class constraints

```haskell
-- Define Shape data type with deriving for Ord and Eq
data Shape = Circle Double | Rectangle Double Double
  deriving (Show, Eq, Ord)

-- Type class Describable
class Describable a where
    describe :: a -> String

-- Implement Describable for Shape
instance Describable Shape where
    describe (Circle r)      = "A circle with radius " ++ show r
    describe (Rectangle w h) = "A rectangle with width " ++ show w ++ " and height " ++ show h

-- Implement Describable for Int (for demonstration)
instance Describable Int where
    describe = show

-- Function that takes two values that are both Describable and Ord,
-- returns the description of the larger one
describeAndCompare :: (Describable a, Ord a) => a -> a -> String
describeAndCompare x y
  | x >= y    = describe x
  | otherwise = describe y

-- Main function to test describeAndCompare
main :: IO ()
main = do
    let c1 = Circle 5.0
        c2 = Circle 3.5
        r1 = Rectangle 4 6
        r2 = Rectangle 4 5
        n1 = 10 :: Int
        n2 = 20 :: Int

    putStrLn $ describeAndCompare c1 c2  -- Should describe Circle 5.0
    putStrLn $ describeAndCompare r1 r2  -- Should describe Rectangle 4 6
    putStrLn $ describeAndCompare n1 n2  -- Should describe 20
```

---

### How to run

1. Save as `DescribeCompare.hs`
2. Compile and run:

```bash
ghc DescribeCompare.hs -o describecompare
./describecompare
```

---

### Expected output

```
A circle with radius 5.0
A rectangle with width 4.0 and height 6.0
20
```

---

**Note:**

* `Shape` derives `Ord` based on the order of constructors and their parameters.
* We added a `Describable` instance for `Int` just to demonstrate using `describeAndCompare` on integers.

