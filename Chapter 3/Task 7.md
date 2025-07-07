HC3T7 - Advanced Task 7: Determine the season based on the month using guards

```haskell
module Main where

season :: Int -> String
season month
  | month == 12 || month == 1 || month == 2   = "Winter"
  | month == 3  || month == 4 || month == 5   = "Spring"
  | month == 6  || month == 7 || month == 8   = "Summer"
  | month == 9  || month == 10 || month == 11 = "Autumn"
  | otherwise = "Invalid month"

main :: IO ()
main = do
  putStrLn $ "season 3 = " ++ season 3
  putStrLn $ "season 7 = " ++ season 7
  putStrLn $ "season 11 = " ++ season 11
```

---

### Explanation:

* Uses guards (`|`) to match the month to its corresponding season.
* Includes a fallback case (`otherwise`) for invalid input (e.g., month < 1 or > 12).

### Output when run:

```
season 3 = Spring
season 7 = Summer
season 11 = Autumn
```

