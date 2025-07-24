HC15T7: Velocity Calculation with Optionals and Parsing Handling

1. Prompts the user for distance and time.
2. Uses `readMaybe` to safely parse both inputs.
3. Calculates the velocity (distance / time).
4. Handles parsing errors and divide-by-zero safely using `Maybe`.

---

### ✅ Full Haskell Example: Velocity Calculator with Safe Parsing

```haskell
import Text.Read (readMaybe)

-- Safe division using Maybe
safeDiv :: Double -> Double -> Maybe Double
safeDiv _ 0 = Nothing
safeDiv x y = Just (x / y)

-- Compute velocity given optional distance and time
computeVelocity :: Maybe Double -> Maybe Double -> Maybe Double
computeVelocity (Just d) (Just t) = safeDiv d t
computeVelocity _ _ = Nothing

main :: IO ()
main = do
    putStrLn "Enter distance (in meters):"
    distStr <- getLine
    putStrLn "Enter time (in seconds):"
    timeStr <- getLine

    let mDist = readMaybe distStr :: Maybe Double
        mTime = readMaybe timeStr :: Maybe Double

    case computeVelocity mDist mTime of
        Just v  -> putStrLn $ "Velocity: " ++ show v ++ " m/s"
        Nothing -> putStrLn "Error: Invalid input or time cannot be zero."
```

---

### 🔍 Features

* Uses `readMaybe` to avoid crashes from invalid number inputs.
* Uses `safeDiv` to handle divide-by-zero with `Maybe`.
* Clean and idiomatic Haskell style with clear separation of concerns.

---

### 🧪 Sample Runs

**Example 1 (valid input):**

```
Enter distance (in meters):
100
Enter time (in seconds):
20
Velocity: 5.0 m/s
```

**Example 2 (invalid number):**

```
Enter distance (in meters):
abc
Enter time (in seconds):
20
Error: Invalid input or time cannot be zero.
```

**Example 3 (divide by zero):**

```
Enter distance (in meters):
100
Enter time (in seconds):
0
Error: Invalid input or time cannot be zero.
```

---


