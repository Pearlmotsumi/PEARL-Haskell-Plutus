HC16T1: Reverse a String

---

### ✅ Haskell Code (with `reverseString` function and `main`)

```haskell
-- Define the function to reverse a string
reverseString :: String -> String
reverseString str = reverse str

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter a string to reverse:"
    input <- getLine
    let reversed = reverseString input
    putStrLn $ "Reversed string: " ++ reversed
```

---

### 📌 How It Works:

* The `reverseString` function uses Haskell's built-in `reverse` function.
* `main` prompts the user, reads a line of input, reverses it, and prints the result.

---

### 🧪 Sample Run

```
Enter a string to reverse:
haskell
Reversed string: lleksah
```


