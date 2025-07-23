HC14T7: Library Component in Cabal

---

### ✅ Project Layout

```
my-project/
├── my-project.cabal     -- Modified Cabal file (library + exe)
├── app/
│   └── Main.hs          -- Main program
├── src/
│   └── Greeting.hs      -- Library module
├── README.md
├── LICENSE
├── CHANGELOG.md
└── Setup.hs
```

---

### ✅ 1. `src/Greeting.hs` (Library Module)

```haskell
module Greeting (greet) where

greet :: String -> IO ()
greet name = putStrLn ("Hello, " ++ name ++ "! This is from the shared library.")
```

---

### ✅ 2. `app/Main.hs` (Executable)

```haskell
module Main where

import Greeting (greet)

main :: IO ()
main = greet "Haskell Developer"
```

---

### ✅ 3. Modify `my-project.cabal`

Here’s an example `my-project.cabal` supporting **both a library and an executable**:

```cabal
cabal-version:       >=1.10
name:                my-project
version:             0.1.0.0
build-type:          Simple
license:             BSD-3-Clause
author:              Your Name
maintainer:          you@example.com
category:            Example

library
  exposed-modules:     Greeting
  hs-source-dirs:      src
  build-depends:       base >=4.7 && <5
  default-language:    Haskell2010

executable my-project-exe
  main-is:             Main.hs
  hs-source-dirs:      app
  build-depends:       base >=4.7 && <5, my-project
  default-language:    Haskell2010
```

> 🔎 Note: The `executable` block depends on the library via `my-project`.

---

### ✅ 4. Build & Run the Project

```bash
cabal build
cabal run my-project-exe
```

---

### 🧪 Output

```
Hello, Haskell Developer! This is from the shared library.
```

---

