HC15T10: Hybrid Error Handling with Either and IO

* ✅ `Either` for **input validation and business logic errors**
* ✅ `try` from `Control.Exception` for **IO exception handling**

---

### 🚀 Velocity Program with Hybrid Error Handling (`Either` + `IO`)

```haskell
{-# LANGUAGE ScopedTypeVariables #-}

import Control.Exception (try, IOException)
import Text.Read (readEither)

-- Function that computes velocity and returns errors using Either
computeVelocity :: Double -> Double -> Either String Double
computeVelocity distance time
    | time == 0 = Left "Time cannot be zero (division by zero)."
    | distance < 0 || time < 0 = Left "Distance and time must be non-negative."
    | otherwise = Right (distance / time)

-- Safely read a value using Either
readDouble :: String -> Either String Double
readDouble s = case readEither s of
    Right x -> Right x
    Left _  -> Left $ "Invalid number: \"" ++ s ++ "\""

-- Main program with IO and Either error handling
main :: IO ()
main = do
    putStrLn "Enter input filename (containing distance and time):"
    fileName <- getLine

    -- Try to read the file content (IO exception handling)
    fileResult <- try (readFile fileName) :: IO (Either IOException String)

    case fileResult of
        Left ioErr -> putStrLn $ "File error: " ++ show ioErr
        Right content -> 
            case lines content of
                (d:t:_) -> do
                    let result = do
                            distance <- readDouble d
                            time     <- readDouble t
                            computeVelocity distance time

                    case result of
                        Left err     -> putStrLn $ "Error: " ++ err
                        Right velocity -> putStrLn $ "Velocity: " ++ show velocity ++ " units/time"
                _ -> putStrLn "Error: File must contain at least two lines (distance and time)."
```

---

### 📄 Example Input File (`input.txt`)

```
100
20
```

---

### ✅ Sample Run (Correct Input)

```
Enter input filename (containing distance and time):
input.txt
Velocity: 5.0 units/time
```

---

### ❌ Sample Run (Time is 0)

```
Enter input filename (containing distance and time):
input.txt
Error: Time cannot be zero (division by zero).
```

---

### ❌ Sample Run (File Not Found)

```
Enter input filename (containing distance and time):
missing.txt
File error: missing.txt: openFile: does not exist (No such file or directory)
```

---


