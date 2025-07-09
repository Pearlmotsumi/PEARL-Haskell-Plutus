HC4T6 - Task 6: Identify List Contents Using Pattern Matching

---

### ✅ Haskell Code:

```haskell
-- Define whatsInsideThisList using pattern matching
whatsInsideThisList :: [a] -> String
whatsInsideThisList []       = "The list is empty."
whatsInsideThisList [_]      = "The list has one element."
whatsInsideThisList [_, _]   = "The list has two elements."
whatsInsideThisList _        = "The list has many elements."

-- Main function to test whatsInsideThisList
main :: IO ()
main = do
    printTest []               -- Empty list
    printTest [42]             -- One element
    printTest ["hello", "hi"] -- Two elements
    printTest [1,2,3,4]        -- Many elements

-- Helper function to display result
printTest :: Show a => [a] -> IO ()
printTest lst = do
    putStrLn $ "List: " ++ show lst
    putStrLn $ "Message: " ++ whatsInsideThisList lst
    putStrLn ""
```

---

### 🛠 How to Run:

1. Save to a file like `WhatsInsideList.hs`
2. Compile and run:

   ```bash
   ghc WhatsInsideList.hs -o whatsinside
   ./whatsinside
   ```

---

### 🧾 Sample Output:

```
List: []
Message: The list is empty.

List: [42]
Message: The list has one element.

List: ["hello","hi"]
Message: The list has two elements.

List: [1,2,3,4]
Message: The list has many elements.
```

