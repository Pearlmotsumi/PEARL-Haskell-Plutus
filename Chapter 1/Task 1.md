HC1T1 - Task 1: Function Composition

* `double`: Multiplies a number by 2
* `increment`: Increases a number by 1
* `doubleThenIncrement`: Uses **function composition** to apply `double` first, then `increment`

---

### ✅ Haskell Code

```haskell
-- Define the double function
double :: Int -> Int
double x = x * 2

-- Define the increment function
increment :: Int -> Int
increment x = x + 1

-- Compose the two: apply double first, then increment
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double

-- Main function to test
main :: IO ()
main = do
    let num = 7
    putStrLn $ "Original number: " ++ show num
    putStrLn $ "After double: " ++ show (double num)
    putStrLn $ "After increment: " ++ show (increment num)
    putStrLn $ "After doubleThenIncrement: " ++ show (doubleThenIncrement num)
```

---

### ▶ How to Run the Code

1. Save this as `Main.hs`
2. Compile it using:

   ```bash
   ghc Main.hs
   ```
3. Run it:

   ```bash
   ./Main
   ```

---

### ✅ Sample Output

```
Original number: 7
After double: 14
After increment: 8
After doubleThenIncrement: 15
```

This demonstrates the **function composition** (`.`) in action: `doubleThenIncrement = increment . double` means `increment (double x)`.


