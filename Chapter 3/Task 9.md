HC3T9 - Advanced Task 9: Find the maximum of three numbers using let

```haskell
module Main where

maxOfThree :: Int -> Int -> Int -> Int
maxOfThree a b c =
  let maxAB = max a b
      maxABC = max maxAB c
  in maxABC

main :: IO ()
main = do
  putStrLn $ "maxOfThree 10 20 15 = " ++ show (maxOfThree 10 20 15)
  putStrLn $ "maxOfThree 5 25 10 = " ++ show (maxOfThree 5 25 10)
```

---

### Explanation:

* `maxAB` stores the maximum of `a` and `b`.
* `maxABC` compares that with `c` to get the final maximum.
* Uses the built-in `max` function.

### Expected Output:

```
maxOfThree 10 20 15 = 20
maxOfThree 5 25 10 = 25
```

 
