HC1T2 - Task 2: Pure Function Example

---

### ✅ Haskell Code

```haskell
-- Define the circleArea function
circleArea :: Floating a => a -> a
circleArea r = pi * r * r

-- Main function to test circleArea
main :: IO ()
main = do
    let radius = 5.0
    putStrLn $ "Given radius: " ++ show radius
    putStrLn $ "Area of the circle: " ++ show (circleArea radius)
```

---

### ▶ How to Run

1. Save as `CircleArea.hs`
2. Compile:

   ```bash
   ghc CircleArea.hs
   ```
3. Run:

   ```bash
   ./CircleArea
   ```

---

### ✅ Sample Output

```
Given radius: 5.0
Area of the circle: 78.53981633974483
```

---

This function is **pure**:

* It depends only on its input `r`
* It has no side effects
* It always returns the same output for the same input


