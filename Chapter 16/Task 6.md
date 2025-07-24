HC16T6: nth Fibonacci Number

---

### ✅ Haskell Code: `nth` Fibonacci Number

```haskell
-- Define a recursive function to calculate the nth Fibonacci number
fibonacci :: Int -> Integer
fibonacci n
    | n <= 0    = 0
    | n == 1    = 1
    | otherwise = fibonacci (n - 1) + fibonacci (n - 2)

-- Main function to prompt the user and show the result
main :: IO ()
main = do
    putStrLn "Enter a position (n) to get the nth Fibonacci number:"
    input <- getLine
    let n = read input :: Int
    let result = fibonacci n
    putStrLn $ "Fibonacci number at position " ++ show n ++ " is " ++ show result
```

---

### 🧪 Example Run

```
Enter a position (n) to get the nth Fibonacci number:
7
Fibonacci number at position 7 is 13
```

---


