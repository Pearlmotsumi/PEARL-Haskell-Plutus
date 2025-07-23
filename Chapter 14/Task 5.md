HC14T5: Custom Data Type and Pattern Matching with @

* Defines a custom data type `Result a`
* Demonstrates **pattern matching with the `@` symbol** to bind the entire value while matching on its structure
* Uses `main` to test it

---

### ✅ Haskell Code

```haskell
module Main where

-- Define a custom data type
data Result a = Success a | Error String deriving Show

-- Function that pattern matches using the @ symbol
describeResult :: Result Int -> String
describeResult res@(Success val) = "Matched " ++ show res ++ " with value: " ++ show val
describeResult err@(Error msg)   = "Matched " ++ show err ++ " with error: " ++ msg

main :: IO ()
main = do
  let r1 = Success 42
      r2 = Error "Something went wrong"
  putStrLn $ describeResult r1
  putStrLn $ describeResult r2
```

---

### 🧪 How to Run

1. Save as `Main.hs`
2. Compile and run:

```bash
ghc Main.hs -o resultDemo
./resultDemo
```

---

### 💡 Output Example

```
Matched Success 42 with value: 42
Matched Error "Something went wrong" with error: Something went wrong
```

The `@` symbol lets you refer to the entire matched value (`res`, `err`) while also deconstructing its parts (`val`, `msg`).

