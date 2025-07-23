HC14T3: NumericUnderscores Extension

* Enables the `NumericUnderscores` language extension
* Defines variables with large numbers using underscores for readability
* Prints them in the `main` function

```haskell
{-# LANGUAGE NumericUnderscores #-}

module Main where

main :: IO ()
main = do
  let bigNumber1 = 1_000_000_000 :: Integer
      bigNumber2 = 123_456_789_012_345 :: Integer
  putStrLn $ "Big number 1: " ++ show bigNumber1
  putStrLn $ "Big number 2: " ++ show bigNumber2
```

---

### How to run

1. Save as `Main.hs`
2. Run with GHC (make sure your GHC version supports `NumericUnderscores`, GHC 9.2+):

```bash
ghc Main.hs
./Main
```

---

### Output

```
Big number 1: 1000000000
Big number 2: 123456789012345
```


