HC16T2: Palindrome Checker

---

### ✅ Haskell Code (with `isPalindrome` and `main`)

```haskell
-- Define the palindrome checking function
isPalindrome :: String -> Bool
isPalindrome str = cleaned == reverse cleaned
  where
    cleaned = map toLower $ filter isAlphaNum str

-- Needed imports for character filtering
import Data.Char (toLower, isAlphaNum)

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter a string to check if it's a palindrome:"
    input <- getLine
    if isPalindrome input
        then putStrLn "Yes, it's a palindrome!"
        else putStrLn "No, it's not a palindrome."
```

---

### 🧪 Example Usage

```
Enter a string to check if it's a palindrome:
Madam
Yes, it's a palindrome!
```

---

### 🔍 Notes:

* This version **ignores case and non-alphanumeric characters** (so "A man, a plan, a canal: Panama" works).
* `toLower` and `isAlphaNum` come from `Data.Char`.

