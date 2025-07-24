HC15T2: Self-Driving AI Car System

---

### ✅ Behavior:

* **"Red"** → Stop
* **"Yellow"** → Slow down
* **"Green"** → Go
* Any other input → Invalid signal

---

### ✅ Full Working Code:

```haskell
-- SelfDrivingCar.hs

-- Define TrafficLight as a data type
data TrafficLight = Red | Yellow | Green | Unknown
  deriving (Show, Eq)

-- Convert user input (String) to TrafficLight
parseTrafficLight :: String -> TrafficLight
parseTrafficLight input = case map toLower input of
    "red"    -> Red
    "yellow" -> Yellow
    "green"  -> Green
    _        -> Unknown
  where
    toLower c
      | 'A' <= c && c <= 'Z' = toEnum (fromEnum c + 32)
      | otherwise            = c

-- Define car's response based on the traffic light
carResponse :: TrafficLight -> String
carResponse Red     = "Stopping... 🚗🛑"
carResponse Yellow  = "Slowing down... 🚗⚠️"
carResponse Green   = "Going! 🚗💨"
carResponse Unknown = "Unrecognized signal. Please try again."

-- Main function to interact with user
main :: IO ()
main = do
    putStrLn "=== Self-Driving AI Car ==="
    putStrLn "Enter traffic light color (Red, Yellow, Green):"
    input <- getLine
    let light = parseTrafficLight input
    putStrLn $ carResponse light
```

---

### ✅ How to Run:

1. Save the file as `SelfDrivingCar.hs`
2. Compile and run it:

```bash
ghc SelfDrivingCar.hs -o car
./car
```

---

### ✅ Sample Interaction:

```
=== Self-Driving AI Car ===
Enter traffic light color (Red, Yellow, Green):
Green
Going! 🚗💨
```

---

