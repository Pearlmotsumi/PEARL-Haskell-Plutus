HC3T5 - Task 5: Determine the type of a triangle using guards

```haskell
module Main where

triangleType :: Float -> Float -> Float -> String
triangleType a b c
  | a == b && b == c         = "Equilateral"
  | a == b || b == c || a == c = "Isosceles"
  | otherwise                = "Scalene"

main :: IO ()
main = do
  putStrLn $ "triangleType 3 3 3 = " ++ triangleType 3 3 3
  putStrLn $ "triangleType 5 5 8 = " ++ triangleType 5 5 8
  putStrLn $ "triangleType 6 7 8 = " ++ triangleType 6 7 8
```

---

### Explanation:

* `a == b && b == c`: all sides equal → **Equilateral**
* any two sides equal → **Isosceles**
* none equal → **Scalene**

### Output when run:

```
triangleType 3 3 3 = Equilateral
triangleType 5 5 8 = Isosceles
triangleType 6 7 8 = Scalene
```


