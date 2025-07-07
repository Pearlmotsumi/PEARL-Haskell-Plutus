HC2T3 - Task 3: Immutable Variables

```haskell
module Main where

-- Immutable variables
myAge :: Int
myAge = 30

piValue :: Double
piValue = 3.14159

greeting :: String
greeting = "Hello, Haskell!"

isHaskellFun :: Bool
isHaskellFun = True

main :: IO ()
main = do
    putStrLn $ "myAge: " ++ show myAge
    putStrLn $ "piValue: " ++ show piValue
    putStrLn $ "greeting: " ++ greeting
    putStrLn $ "isHaskellFun: " ++ show isHaskellFun

    -- Uncommenting the following line will cause a compilation error,
    -- because variables are immutable in Haskell.
    -- myAge = 31

    putStrLn "Attempting to modify myAge would cause a compilation error because Haskell variables are immutable."
```

---

### What happens if you try to modify?

If you uncomment the line `myAge = 31` inside `main` (or anywhere else after the initial declaration), GHC will complain with an error like:

```
error: Multiple declarations of ‘myAge’
```

or

```
error: Variable ‘myAge’ is already defined and cannot be reassigned.
```

Haskell variables are *immutable* — once defined, their value cannot be changed.

---


