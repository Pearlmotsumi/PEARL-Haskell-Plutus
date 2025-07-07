HC2T6 - Task 6: Understanding Int vs Integer

```haskell
module Main where

-- 2^62 fits in Int on many 64-bit systems but be cautious with overflow
smallNumber :: Int
smallNumber = 2 ^ 62

-- Integer can hold arbitrarily large numbers
bigNumber :: Integer
bigNumber = 2 ^ 127

main :: IO ()
main = do
    putStrLn $ "smallNumber (2^62 :: Int): " ++ show smallNumber
    putStrLn $ "bigNumber (2^127 :: Integer): " ++ show bigNumber

    -- Note: Evaluating 2^64 :: Int in GHCi will cause overflow
    -- because Int usually has a 64-bit signed range: -(2^63) to (2^63 - 1).
    putStrLn "Evaluating (2^64 :: Int) in GHCi causes overflow and results in a negative number due to integer overflow."
```

---

### About `2^64 :: Int` in GHCi

If you run this in GHCi:

```ghci
Prelude> 2^64 :: Int
```

You typically get a **negative number** because `Int` is a fixed-size signed integer (usually 64-bit on modern machines). The value `2^64` exceeds the maximum positive `Int` value (`2^63 - 1`), causing overflow and wrapping around.

For arbitrarily large integers, you should use `Integer` instead:

```ghci
Prelude> 2^64 :: Integer
18446744073709551616
```

---


