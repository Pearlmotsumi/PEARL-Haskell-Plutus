HC3T8 - Advanced Task 8: Calculate BMI and return category using where

```haskell
module Main where

bmiCategory :: Float -> Float -> String
bmiCategory weight height
  | bmi < 18.5 = "Underweight"
  | bmi < 25   = "Normal"
  | bmi < 30   = "Overweight"
  | otherwise  = "Obese"
  where
    bmi = weight / (height ^ 2)

main :: IO ()
main = do
  putStrLn $ "bmiCategory 70 1.75 = " ++ bmiCategory 70 1.75
  putStrLn $ "bmiCategory 90 1.8 = " ++ bmiCategory 90 1.8
```

---

### Explanation:

* `bmi = weight / height^2` is computed in the `where` clause for clarity and reuse.
* Guards classify the BMI value:

  * `< 18.5`: "Underweight"
  * `< 25`: "Normal"
  * `< 30`: "Overweight"
  * `>= 30`: "Obese"

### Expected Output:

```
bmiCategory 70 1.75 = Normal
bmiCategory 90 1.8 = Overweight
```


