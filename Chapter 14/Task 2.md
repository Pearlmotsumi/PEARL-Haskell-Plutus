HC14T2: Add Dependency and Print Random Number

---

### Step 1: Modify your `.cabal` file

Add `random` to the `build-depends` field under your executable section. For example:

```cabal
executable hello-cabal
  main-is:             Main.hs
  hs-source-dirs:      app
  build-depends:       base >=4.7 && <5, random
  default-language:    Haskell2010
```

---

### Step 2: Update `app/Main.hs`

Here’s a program that prints a random number between 1 and 100:

```haskell
module Main where

import System.Random (randomRIO)

main :: IO ()
main = do
  num <- randomRIO (1, 100) :: IO Int
  putStrLn $ "Random number between 1 and 100: " ++ show num
```

---

### Step 3: Build and run

Run:

```bash
cabal build
cabal run
```

---

### Output Example

```
Random number between 1 and 100: 42
```

---

