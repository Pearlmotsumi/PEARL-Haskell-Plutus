HC15T1: Handle Exceptions for File Reading and Velocity Calculation

1. **Reads a file** containing distance and time values (one per line, format: `distance time`),
2. **Calculates velocity** (`velocity = distance / time`),
3. **Handles exceptions** such as:

   * File not found,
   * Invalid content (non-numeric or missing values),
   * Division by zero.

---

### ✅ Example File Content (`input.txt`)

```
100 10
200 0
bad data
150 30
```

---

### ✅ Haskell Code (Complete with `main`)

```haskell
import System.IO
import System.IO.Error
import Control.Exception
import Text.Read (readMaybe)

-- Function to calculate velocity from a line like "distance time"
processLine :: String -> Either String Double
processLine line =
    case words line of
        [dStr, tStr] ->
            case (readMaybe dStr, readMaybe tStr) of
                (Just d, Just t) ->
                    if t == 0
                        then Left "Error: Time cannot be zero (division by zero)."
                        else Right (d / t)
                _ -> Left "Error: Invalid number format."
        _ -> Left "Error: Line must contain exactly two values (distance and time)."

-- Safe file reading with error handling
safeReadFile :: FilePath -> IO (Either IOError String)
safeReadFile = try . readFile

main :: IO ()
main = do
    putStrLn "Enter the file name (e.g., input.txt):"
    fileName <- getLine

    result <- safeReadFile fileName
    case result of
        Left err -> putStrLn $ "Failed to read file: " ++ ioeGetErrorString err
        Right contents -> do
            let linesOfFile = lines contents
            putStrLn "\nProcessing lines...\n"
            mapM_ printResult (zip [1..] linesOfFile)

  where
    printResult (n, line) =
        case processLine line of
            Right v  -> putStrLn $ "Line " ++ show n ++ ": Velocity = " ++ show v
            Left err -> putStrLn $ "Line " ++ show n ++ ": " ++ err
```

---

### ✅ How to Run

1. Save the Haskell code as `Velocity.hs`.
2. Create `input.txt` with valid and invalid entries.
3. Compile and run:

```bash
ghc Velocity.hs -o velocity
./velocity
```

Then input:

```
input.txt
```

---

### ✅ Sample Output

```
Enter the file name (e.g., input.txt):
input.txt

Processing lines...

Line 1: Velocity = 10.0
Line 2: Error: Time cannot be zero (division by zero).
Line 3: Error: Invalid number format.
Line 4: Velocity = 5.0
```

---

