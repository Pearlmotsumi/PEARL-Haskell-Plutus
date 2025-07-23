HC14T6: Project Structure: src and app

```
my-project/
├── app/
│   └── Main.hs           -- Entry point (main module)
├── src/
│   └── Greeting.hs       -- Additional module
├── my-project.cabal      -- Cabal config file
├── CHANGELOG.md
├── LICENSE
├── README.md
└── Setup.hs
```

---

### ✅ Step 1: Create Project Structure

Run the following command:

```bash
cabal init --non-interactive --minimal --package-name=my-project --exe
```

Then move the files:

```bash
mkdir src
mkdir app
mv Main.hs app/Main.hs
```

---

### ✅ Step 2: `app/Main.hs`

```haskell
module Main where

import Greeting (greet)

main :: IO ()
main = greet "Haskell Developer"
```

---

### ✅ Step 3: `src/Greeting.hs`

```haskell
module Greeting (greet) where

greet :: String -> IO ()
greet name = putStrLn ("Hello, " ++ name ++ "! Welcome to the Cabal project.")
```

---

### ✅ Step 4: Modify `.cabal` File

In `my-project.cabal`, change the executable section to:

```cabal
executable my-project
  main-is:             Main.hs
  hs-source-dirs:      app, src
  build-depends:       base >=4.7 && <5
  default-language:    Haskell2010
```

---

### ✅ Step 5: Build and Run

```bash
cabal build
cabal run
```

---

### 🧪 Output

```
Hello, Haskell Developer! Welcome to the Cabal project.
```


