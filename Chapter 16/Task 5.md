HC16T5: Uppercase String

---

### ✅ Haskell Code: Convert String to Uppercase

```haskell
import Data.Char (toUpper)

-- Function to convert a string to uppercase
toUppercase :: String -> String
toUppercase = map toUpper

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter a string:"
    input <- getLine
    let result = toUppercase input
    putStrLn $ "Uppercase: " ++ result
```

---

### 🧪 Example Run

```
Enter a string:
hello, haskell!
Uppercase: HELLO, HASKELL!
```

---

### 🔍 How It Works:

* `toUpper` is imported from `Data.Char` to convert each character.
* `map toUpper` applies `toUpper` to every character in the string.


