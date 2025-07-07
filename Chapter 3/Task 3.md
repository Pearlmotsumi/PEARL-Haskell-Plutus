HC3T3 - Task 3: Convert an RGB color to a hex string using let bindings

```haskell
module Main where

import Numeric (showHex)
import Data.Char (toUpper)

-- Converts an Int (0-255) to a two-character uppercase hex string
toTwoCharHex :: Int -> String
toTwoCharHex n = let hex = showHex n ""
                     padded = if length hex == 1 then '0':hex else hex
                 in map toUpper padded

-- Converts an (R,G,B) tuple to a hex color string like "#RRGGBB"
rgbToHex :: (Int, Int, Int) -> String
rgbToHex (r, g, b) = let rHex = toTwoCharHex r
                         gHex = toTwoCharHex g
                         bHex = toTwoCharHex b
                     in "#" ++ rHex ++ gHex ++ bHex

main :: IO ()
main = do
    putStrLn $ "rgbToHex (255, 0, 127) = " ++ rgbToHex (255, 0, 127)
    putStrLn $ "rgbToHex (0, 255, 64) = " ++ rgbToHex (0, 255, 64)
```

---

### What this does:

* `toTwoCharHex` converts a number 0–255 to a two-digit hex string, padding with a leading zero if needed and converting letters to uppercase.
* `rgbToHex` uses `let` bindings to convert each color component, then concatenates them with a leading `#`.
* `main` tests the function with your examples.

### Expected output:

```
rgbToHex (255, 0, 127) = #FF007F
rgbToHex (0, 255, 64) = #00FF40
```


