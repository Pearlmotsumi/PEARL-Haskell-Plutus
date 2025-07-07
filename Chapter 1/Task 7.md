HC1T7 - Task 7: Converting Fahrenheit to Celsius

```haskell
-- Function to convert Fahrenheit to Celsius
fToC :: Float -> Float
fToC f = (f - 32) * 5 / 9

-- Main function to test fToC
main :: IO ()
main = do
    let fahrenheit = 98.6
    let celsius = fToC fahrenheit
    putStrLn ("Temperature in Fahrenheit: " ++ show fahrenheit)
    putStrLn ("Converted to Celsius: " ++ show celsius)
```

### Expected Output:

```
Temperature in Fahrenheit: 98.6
Converted to Celsius: 37.0
```

### How to Run:

1. Save the file as `FahrenheitToCelsius.hs`
2. Compile and run:

   ```bash
   ghc FahrenheitToCelsius.hs -o fToC
   ./fToC
   ```

