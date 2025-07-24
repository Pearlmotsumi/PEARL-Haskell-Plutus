HC16T3: Factorial

---

### ✅ Haskell Code (Factorial Function with `main`)

```haskell
-- Define the factorial function using recursion
factorial :: Integer -> Integer
factorial 0 = 1
factorial n = n * factorial (n - 1)

-- Main function to test it
main :: IO ()
main = do
    putStrLn "Enter a non-negative integer:"
    input <- getLine
    let number = read input :: Integer
    if number < 0
        then putStrLn "Factorial is not defined for negative numbers."
        else putStrLn $ "Factorial of " ++ show number ++ " is " ++ show (factorial number)
```

---

### 🧪 Example Run

```
Enter a non-negative integer:
5
Factorial of 5 is 120
```

---

### 🔍 Notes:

* The function is defined recursively: `factorial n = n * factorial (n - 1)`
* Input is read and converted using `read :: Integer`.
* Handles invalid input like negative numbers with a warning.


