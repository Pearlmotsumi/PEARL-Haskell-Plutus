HC14T4: TypeApplications Extension

* Enables the `TypeApplications` extension
* Defines a function that reads a `String` and converts it to an `Int` using `read @Int`
* Uses `main` to get user input and demonstrate the conversion

---

### ✅ Haskell Code

```haskell
{-# LANGUAGE TypeApplications #-}

module Main where

convertToInt :: String -> Int
convertToInt = read @Int

main :: IO ()
main = do
  putStrLn "Enter a number:"
  input <- getLine
  let number = convertToInt input
  putStrLn $ "You entered the number: " ++ show number
```

---

### 🧪 How to Run

1. Save this as `Main.hs`
2. Compile and run using GHC:

```bash
ghc Main.hs -o runApp
./runApp
```

---

### 💡 Example Interaction

```
Enter a number:
42
You entered the number: 42
```

---


