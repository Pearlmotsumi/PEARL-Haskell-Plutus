HC3T6 - Advanced Task 6: Check leap year using if-then-else

```haskell
module Main where

isLeapYear :: Int -> Bool
isLeapYear year =
  if year `mod` 400 == 0 then True
  else if year `mod` 100 == 0 then False
  else if year `mod` 4 == 0 then True
  else False

main :: IO ()
main = do
  putStrLn $ "isLeapYear 2000 = " ++ show (isLeapYear 2000)
  putStrLn $ "isLeapYear 1900 = " ++ show (isLeapYear 1900)
  putStrLn $ "isLeapYear 2024 = " ++ show (isLeapYear 2024)
```

---

### Explanation:

* A year divisible by **400** → `True` (leap year)
* A year divisible by **100 but not 400** → `False` (not a leap year)
* A year divisible by **4** → `True` (leap year)
* Otherwise → `False`

### Output when run:

```
isLeapYear 2000 = True
isLeapYear 1900 = False
isLeapYear 2024 = True
```

