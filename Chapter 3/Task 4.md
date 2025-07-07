HC3T4 - Task 4: Calculate the area of a triangle using Heron's formula

```haskell
module Main where

triangleArea :: Float -> Float -> Float -> Float
triangleArea a b c = 
  let s = (a + b + c) / 2
  in sqrt (s * (s - a) * (s - b) * (s - c))

main :: IO ()
main = do
  putStrLn $ "triangleArea 3 4 5 = " ++ show (triangleArea 3 4 5)
  putStrLn $ "triangleArea 7 8 9 = " ++ show (triangleArea 7 8 9)
```

---

### Explanation:

* `s` is the semi-perimeter.
* Heron's formula is applied as `sqrt(s * (s - a) * (s - b) * (s - c))`.

Running this will output:

```
triangleArea 3 4 5 = 6.0
triangleArea 7 8 9 = 26.832815
```

