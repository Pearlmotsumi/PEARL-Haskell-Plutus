HC16T8: Insertion Sort

---

### ✅ Haskell Code: Insertion Sort

```haskell
-- Insertion sort implementation
insertionSort :: [Int] -> [Int]
insertionSort [] = []
insertionSort (x:xs) = insert x (insertionSort xs)

-- Helper function to insert an element into the sorted list
insert :: Int -> [Int] -> [Int]
insert x [] = [x]
insert x (y:ys)
    | x <= y    = x : y : ys
    | otherwise = y : insert x ys

-- Main function to test insertionSort
main :: IO ()
main = do
    putStrLn "Enter a list of integers separated by spaces:"
    input <- getLine
    let nums = map read (words input) :: [Int]
    let sorted = insertionSort nums
    putStrLn $ "Sorted list: " ++ show sorted
```

---

### 🧪 Example Run

```
Enter a list of integers separated by spaces:
5 3 8 1 4
Sorted list: [1,3,4,5,8]
```

---

