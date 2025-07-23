HC14T1: Initialize a Cabal Project

---

### Step 1: Initialize the project

Run in your terminal:

```bash
cabal init
```

During the interactive prompts, choose options like:

* Package name: `hello-cabal` (or your choice)
* Package type: **Executable**
* Main module: `Main.hs`
* Other defaults are fine for a simple project

Alternatively, run non-interactively with:

```bash
cabal init --non-interactive --exe --package-name=hello-cabal
```

This creates a directory with the necessary cabal files and a `Main.hs`.

---

### Step 2: Edit `app/Main.hs`

Replace the contents of `app/Main.hs` (or `Main.hs` depending on the setup) with:

```haskell
module Main where

main :: IO ()
main = putStrLn "Hello, Cabal!"
```

---

### Step 3: Build and run the executable

From your project root, run:

```bash
cabal build
cabal run
```

This will compile the executable and run it, printing:

```
Hello, Cabal!
```

---

### Alternative: Minimal complete example

If you want the **smallest working example** without manual init, create this structure manually:

```
hello-cabal/
├── hello-cabal.cabal
└── app/
    └── Main.hs
```

**hello-cabal.cabal** (minimal content):

```cabal
cabal-version:       2.4
name:                hello-cabal
version:             0.1.0.0
build-type:          Simple

executable hello-cabal
  main-is:             Main.hs
  hs-source-dirs:      app
  default-language:    Haskell2010
```

**app/Main.hs**:

```haskell
module Main where

main :: IO ()
main = putStrLn "Hello, Cabal!"
```

Then from the `hello-cabal` directory, run:

```bash
cabal build
cabal run
```

---


