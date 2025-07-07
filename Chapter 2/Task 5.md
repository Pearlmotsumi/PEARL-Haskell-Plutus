HC2T5 - Task 5: Defining and Using Functions

```haskell
module Main where

-- Function to calculate the area of a circle given the radius
circleArea :: Float -> Float
circleArea r = pi * r * r

-- Function to find the maximum of three Int values
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree x y z
    | x >= y && x >= z = x
    | y >= x && y >= z = y
    | otherwise        = z

main :: IO ()
main = do
    -- Testing circleArea
    putStrLn $ "circleArea 5 = " ++ show (circleArea 5)
    putStrLn $ "circleArea 2.5 = " ++ show (circleArea 2.5)
    putStrLn $ "circleArea 0 = " ++ show (circleArea 0)

    -- Testing maxOfThree
    putStrLn $ "maxOfThree 3 9 7 = " ++ show (maxOfThree 3 9 7)
    putStrLn $ "maxOfThree 10 10 5 = " ++ show (maxOfThree 10 10 5)
    putStrLn $ "maxOfThree (-1) (-5) (-3) = " ++ show (maxOfThree (-1) (-5) (-3))
```

### What this does:

* `circleArea` uses the formula πr² with `pi` from Prelude.
* `maxOfThree` uses guards to determine the maximum of three integers.
* `main` prints the results for different input values.

Running this will output:

```
circleArea 5 = 78.53982
circleArea 2.5 = 19.63495
circleArea 0 = 0.0
maxOfThree 3 9 7 = 9
maxOfThree 10 10 5 = 10
maxOfThree (-1) (-5) (-3) = -1
```

