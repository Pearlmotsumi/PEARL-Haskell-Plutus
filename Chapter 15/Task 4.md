HC15T4: Exception Handler for Traffic Light

* Custom exception type
* `throwIO` for raising the exception
* `handle` function from `Control.Exception` for clean exception handling

---

### ✅ Haskell Code

```haskell
{-# LANGUAGE DeriveDataTypeable #-}

import Control.Exception
import Data.Typeable

-- Define a custom exception type
data TrafficLightException = InvalidTrafficLight String
  deriving (Show, Typeable)

instance Exception TrafficLightException

-- Define TrafficLight data type
data TrafficLight = Red | Yellow | Green
  deriving (Show, Eq)

-- Parse input to TrafficLight or throw exception
parseTrafficLight :: String -> IO TrafficLight
parseTrafficLight input = case map toLower input of
    "red"    -> return Red
    "yellow" -> return Yellow
    "green"  -> return Green
    _        -> throwIO (InvalidTrafficLight input)
  where
    toLower c
      | 'A' <= c && c <= 'Z' = toEnum (fromEnum c + 32)
      | otherwise = c

-- Car behavior depending on traffic light
carResponse :: TrafficLight -> String
carResponse Red    = "Stopping 🛑"
carResponse Yellow = "Slowing down ⚠️"
carResponse Green  = "Driving 💨"

-- Handler function for custom exceptions
handleTrafficLightError :: TrafficLightException -> IO ()
handleTrafficLightError (InvalidTrafficLight val) =
  putStrLn $ "⚠️ Invalid traffic light input: \"" ++ val ++ "\". Please enter Red, Yellow, or Green."

-- Main function using handler
main :: IO ()
main = handle handleTrafficLightError $ do
  putStrLn "=== AI Self-Driving Car System ==="
  putStrLn "Enter traffic light color (Red, Yellow, Green):"
  input <- getLine
  light <- parseTrafficLight input
  putStrLn $ carResponse light
```

---

### 🔍 How it Works

* **`handle handleTrafficLightError`** wraps the main logic.
* If `parseTrafficLight` fails, the exception is caught and handled in `handleTrafficLightError`.

---

### 🧪 Sample Output

**Input:**

```
Green
```

**Output:**

```
Driving 💨
```

**Input:**

```
Blue
```

**Output:**

```
⚠️ Invalid traffic light input: "Blue". Please enter Red, Yellow, or Green.
```

---

