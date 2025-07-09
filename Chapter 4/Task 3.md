HC4T3 - Task 3: Define a gradeComment Function

```haskell
-- Define the gradeComment function using guards
gradeComment :: Int -> String
gradeComment grade
    | grade >= 90 && grade <= 100 = "Excellent!"
    | grade >= 70 && grade <= 89  = "Good job!"
    | grade >= 50 && grade <= 69  = "You passed."
    | grade >= 0  && grade <= 49  = "Better luck next time."
    | otherwise                   = "Invalid grade"

-- Main function to test gradeComment
main :: IO ()
main = do
    putStrLn $ "Grade 95 -> " ++ gradeComment 95
    putStrLn $ "Grade 75 -> " ++ gradeComment 75
    putStrLn $ "Grade 60 -> " ++ gradeComment 60
    putStrLn $ "Grade 30 -> " ++ gradeComment 30
    putStrLn $ "Grade -5 -> " ++ gradeComment (-5)
    putStrLn $ "Grade 105 -> " ++ gradeComment 105
```

---

### ✅ How to Run

1. Save the code in a file, e.g., `GradeComment.hs`
2. Compile and run it using GHC:

   ```bash
   ghc GradeComment.hs -o gradecomment
   ./gradecomment
   ```

---

### 🔍 Expected Output

```
Grade 95 -> Excellent!
Grade 75 -> Good job!
Grade 60 -> You passed.
Grade 30 -> Better luck next time.
Grade -5 -> Invalid grade
Grade 105 -> Invalid grade
```

