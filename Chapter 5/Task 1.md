HC5T1: Using applyTwice

---

### ✅ Haskell Code:

```haskell
-- Define applyThrice: takes a function and an integer, applies the function three times
applyThrice :: (Int -> Int) -> Int -> Int
applyThrice f x = f (f (f x))

-- Example function to use with applyThrice
double :: Int -> Int
double n = 2 * n

-- Main function to test applyThrice
main :: IO ()
main = do
    let result1 = applyThrice double 1         -- double(double(double(1))) = 8
    let result2 = applyThrice (+1) 5           -- (+1)(+1)(+1)(5) = 8
    let result3 = applyThrice (\x -> x * x) 2  -- square(square(square(2))) = 256

    putStrLn $ "applyThrice double 1     = " ++ show result1
    putStrLn $ "applyThrice (+1) 5       = " ++ show result2
    putStrLn $ "applyThrice (x -> x*x) 2 = " ++ show result3
```

---

### 🛠 How to Run

1. Save the file as `ApplyThrice.hs`
2. Compile and run it:

   ```bash
   ghc ApplyThrice.hs -o applythrice
   ./applythrice
   ```

---

### 🧾 Sample Output

```
applyThrice double 1     = 8
applyThrice (+1) 5       = 8
applyThrice (x -> x*x) 2 = 256
```


