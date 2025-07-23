HC14T10: Cabal Test Suite

* A project structure with `app`, `src`, and `test` directories
* A library module (`CharCount`) with the `counts` function
* A test suite using **HUnit**
* A `.cabal` file configuration

---

### ✅ Directory Structure

```
myproject/
├── app/
│   └── Main.hs
├── src/
│   └── CharCount.hs
├── test/
│   └── CharCountTest.hs
├── myproject.cabal
└── cabal.project
```

---

### ✅ Step 1: `src/CharCount.hs`

```haskell
module CharCount (counts) where

import Data.List (group, sort)

-- Count frequency of each character in a string
counts :: String -> [(Char, Int)]
counts str = map (\g -> (head g, length g)) . group . sort $ str
```

---

### ✅ Step 2: `app/Main.hs`

```haskell
module Main where

import CharCount

main :: IO ()
main = do
    putStrLn "Enter a string:"
    input <- getLine
    print (counts input)
```

---

### ✅ Step 3: `test/CharCountTest.hs`

```haskell
module Main (main) where

import Test.HUnit
import CharCount (counts)

-- Define test cases
testCounts :: Test
testCounts = TestList
  [ "Empty string" ~: counts "" ~?= []
  , "Single char" ~: counts "a" ~?= [('a', 1)]
  , "Multiple chars" ~: counts "banana" ~?= [('a', 3), ('b', 1), ('n', 2)]
  , "Unordered input" ~: counts "dcba" ~?= [('a',1),('b',1),('c',1),('d',1)]
  ]

main :: IO ()
main = do
  counts <- runTestTT testCounts
  if errors counts + failures counts == 0 then
    putStrLn "All tests passed!"
  else
    putStrLn "Some tests failed."
```

---

### ✅ Step 4: `myproject.cabal`

Make sure your `.cabal` file includes:

```cabal
cabal-version:       >=1.10
name:                myproject
version:             0.1.0.0
build-type:          Simple

library
  exposed-modules:     CharCount
  hs-source-dirs:      src
  build-depends:       base >=4.14 && <5
  default-language:    Haskell2010

executable myproject-exe
  main-is:             Main.hs
  hs-source-dirs:      app
  build-depends:       base >=4.14 && <5,
                       myproject
  default-language:    Haskell2010

test-suite myproject-test
  type:                exitcode-stdio-1.0
  main-is:             CharCountTest.hs
  hs-source-dirs:      test
  build-depends:       base >=4.14 && <5,
                       myproject,
                       HUnit
  default-language:    Haskell2010
```

---

### ✅ Step 5: Build and Run

```bash
cabal build
cabal test
```

---

### 🧪 Expected Test Output

```
Running 4 tests...
### Test "Empty string": passed
### Test "Single char": passed
### Test "Multiple chars": passed
### Test "Unordered input": passed
All tests passed!
```

---

