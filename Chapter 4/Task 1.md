HC4T1 - Task 1: Define a weatherReport Function

```haskell
-- Define the weatherReport function
weatherReport :: String -> String
weatherReport "sunny"  = "It's a bright and beautiful day!"
weatherReport "rainy"  = "Don't forget your umbrella!"
weatherReport "cloudy" = "A bit gloomy, but no rain yet!"
weatherReport _        = "Weather unknown"

-- Main function to test the weatherReport function
main :: IO ()
main = do
    putStrLn $ "sunny  -> " ++ weatherReport "sunny"
    putStrLn $ "rainy  -> " ++ weatherReport "rainy"
    putStrLn $ "cloudy -> " ++ weatherReport "cloudy"
    putStrLn $ "windy  -> " ++ weatherReport "windy"
```

---

### ✅ How to Run

1. Save the code in a file, for example: `WeatherReport.hs`
2. Compile and run it with GHC:

   ```bash
   ghc WeatherReport.hs -o weatherReport
   ./weatherReport
   ```

---

### 🔍 Expected Output

```
sunny  -> It's a bright and beautiful day!
rainy  -> Don't forget your umbrella!
cloudy -> A bit gloomy, but no rain yet!
windy  -> Weather unknown
```

