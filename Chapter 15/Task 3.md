HC15T3: Custom Exception for Traffic Light Errors

---

### ✅ Features:

* Defines a `TrafficLightException` data type.
* Throws the exception on unrecognized input.
* Catches and prints the custom error message.

---

### ✅ Working Example:

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
parseTrafficLight str = case map toLower str of
    "red"    -> return Red
    "yellow" -> return Yellow
    "green"  -> return Green
    _        -> throwIO (InvalidTrafficLight $ "Invalid input: " ++ str)
  where
    toLower c
      | 'A' <= c && c <= 'Z' = toEnum (fromEnum c + 32)
      | otherwise            = c

-- Define car behavior
carResponse :: TrafficLight -> String
carResponse Red    = "Stopping... 🛑"
carResponse Yellow = "Slowing down... ⚠️"
carResponse Green  = "Going! 💨"

-- Main with exception handling
main :: IO ()
main = do
    putStrLn "=== AI Self-Driving Car ==="
    putStrLn "Enter traffic light color (Red, Yellow, Green):"
    input <- getLine
    result <- try (parseTrafficLight input) :: IO (Either TrafficLightException TrafficLight)
    case result of
        Left err -> putStrLn $ "Error: " ++ show err
        Right light -> putStrLn $ carResponse light
```

---

### ✅ Sample Output:

#### Valid Input:

```
Enter traffic light color (Red, Yellow, Green):
Green
Going! 💨
```

#### Invalid Input:

```
Enter traffic light color (Red, Yellow, Green):
Blue
Error: Invalid input: Blue
```

---


