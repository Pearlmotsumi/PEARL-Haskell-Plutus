HC16T4: Filter Even Numbers

---

### ✅ Haskell Code (Filter Even Numbers)

```haskell
-- Define a function that filters even numbers
filterEvens :: [Int] -> [Int]
filterEvens xs = filter even xs

-- Main function to demonstrate usage
main :: IO ()
main = do
    putStrLn "Enter a list of integers separated by spaces:"
    input <- getLine
    let numbers = map read (words input) :: [Int]
    let evens = filterEvens numbers
    putStrLn $ "Even numbers: " ++ show evens
```

---

### 🧪 Example Run

```
Enter a list of integers separated by spaces:
1 2 3 4 5 6 7
Even numbers: [2,4,6]
```

---

### 📝 Notes:

* `filter even xs` keeps only the elements that satisfy `even`.
* `words` splits the input string into a list of strings.
* `map read` converts those strings to integers.

