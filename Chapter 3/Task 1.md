HC3T1 - Task 1: Check if a number is positive, negative, or zero

```haskell
module Main where

checkNumber :: Int -> String
checkNumber n =
  if n > 0 then "Positive"
  else if n < 0 then "Negative"
  else "Zero"

main :: IO ()
main = do
  putStrLn $ "checkNumber 5 = " ++ checkNumber 5
  putStrLn $ "checkNumber (-3) = " ++ checkNumber (-3)
  putStrLn $ "checkNumber 0 = " ++ checkNumber 0
```

### Explanation:

* The function checks the value of `n`:

  * If `n > 0`, it returns `"Positive"`
  * Else if `n < 0`, it returns `"Negative"`
  * Otherwise, it returns `"Zero"`

Running this program will output:

```
checkNumber 5 = Positive
checkNumber (-3) = Negative
checkNumber 0 = Zero
```

