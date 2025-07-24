HC16T7: Element Existence in List

---

### ✅ Haskell Code: Check if an Element Exists in a List

```haskell
-- Function to check if an element exists in a list
elementExists :: Eq a => a -> [a] -> Bool
elementExists _ [] = False
elementExists x (y:ys)
    | x == y    = True
    | otherwise = elementExists x ys

-- Main function to test elementExists
main :: IO ()
main = do
    putStrLn "Enter an element to search for (e.g., 5):"
    input <- getLine
    let elemToFind = read input :: Int
    let list = [1, 2, 3, 4, 5, 6, 7]
    let result = elementExists elemToFind list
    putStrLn $ "Is " ++ show elemToFind ++ " in the list? " ++ show result
```

---

### 🧪 Example Run

```
Enter an element to search for (e.g., 5):
5
Is 5 in the list? True
```

---

