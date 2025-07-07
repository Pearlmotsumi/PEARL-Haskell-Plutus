HC3T2 - Task 2: Determine the grade based on a score using guards

```haskell
module Main where

grade :: Int -> String
grade score
  | score >= 90 = "A"
  | score >= 80 = "B"
  | score >= 70 = "C"
  | score >= 60 = "D"
  | otherwise   = "F"

main :: IO ()
main = do
  putStrLn $ "grade 95 = " ++ grade 95
  putStrLn $ "grade 72 = " ++ grade 72
  putStrLn $ "grade 50 = " ++ grade 50
```

### Explanation:

* The guards check the score starting from the highest grade down.
* If none of the previous conditions match, `otherwise` catches all scores below 60.

Running this will output:

```
grade 95 = A
grade 72 = C
grade 50 = F
```


