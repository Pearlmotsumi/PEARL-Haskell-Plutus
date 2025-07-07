HC2T1 - Task 1: Checking Types in GHCi

1. `42`
   Expected type: `Num a => a` (commonly `Integer` or `Int`)

2. `3.14`
   Expected type: `Fractional a => a` (commonly `Double` or `Float`)

3. `"Haskell"`
   Expected type: `[Char]` (which is a `String`)

4. `'Z'`
   Expected type: `Char`

5. `True && False`
   Expected type: `Bool`

---

Now, I'll provide a working Haskell program that prints the types and the values for these expressions using `:type` in comments and showing the values in `main`.

```haskell
module Main where

main :: IO ()
main = do
    let a = 42          -- :type a is Num a => a, usually Int
    let b = 3.14        -- :type b is Fractional a => a, usually Double
    let c = "Haskell"   -- :type c is [Char] (String)
    let d = 'Z'         -- :type d is Char
    let e = True && False -- :type e is Bool

    putStrLn $ "Value of a (42): " ++ show a
    putStrLn $ "Value of b (3.14): " ++ show b
    putStrLn $ "Value of c (\"Haskell\"): " ++ c
    putStrLn $ "Value of d ('Z'): " ++ [d]
    putStrLn $ "Value of e (True && False): " ++ show e
```

If you want me to show you how these types look exactly when you check in GHCi, here is what you would do inside GHCi:

```ghci
Prelude> :type 42
42 :: Num p => p

Prelude> :type 3.14
3.14 :: Fractional p => p

Prelude> :type "Haskell"
"Haskell" :: [Char]

Prelude> :type 'Z'
'Z' :: Char

Prelude> :type True && False
True && False :: Bool
```


