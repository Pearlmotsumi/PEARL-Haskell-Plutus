HC2T2 - Task 2: Function Type Signatures

```haskell
module Main where

-- Function signatures
add :: Int -> Int -> Int
isEven :: Int -> Bool
concatStrings :: String -> String -> String

-- Function implementations
add x y = x + y

isEven n = n `mod` 2 == 0

concatStrings s1 s2 = s1 ++ s2

main :: IO ()
main = do
    -- Test add
    putStrLn $ "add 3 5 = " ++ show (add 3 5)
    -- Test isEven
    putStrLn $ "isEven 4 = " ++ show (isEven 4)
    putStrLn $ "isEven 7 = " ++ show (isEven 7)
    -- Test concatStrings
    putStrLn $ "concatStrings \"Hello, \" \"world!\" = " ++ concatStrings "Hello, " "world!"
```

You can load this into GHCi or compile it and run it. The output will be:

```
add 3 5 = 8
isEven 4 = True
isEven 7 = False
concatStrings "Hello, " "world!" = Hello, world!
```

