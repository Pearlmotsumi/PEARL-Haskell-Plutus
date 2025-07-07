HC3T10 - Advanced Task 10: Check if a string is a palindrome using recursion and guards

```haskell
module Main where

isPalindrome :: String -> Bool
isPalindrome str
  | length str <= 1             = True
  | head str == last str        = isPalindrome (init (tail str))
  | otherwise                   = False

main :: IO ()
main = do
  putStrLn $ "isPalindrome \"racecar\" = " ++ show (isPalindrome "racecar")
  putStrLn $ "isPalindrome \"haskell\" = " ++ show (isPalindrome "haskell")
  putStrLn $ "isPalindrome \"madam\" = " ++ show (isPalindrome "madam")
```

---

### Explanation:

* If the string has 0 or 1 characters → it's a palindrome.
* If the first and last characters match → recursively check the middle part.
* Otherwise → it's not a palindrome.

---

### Output when run:

```
isPalindrome "racecar" = True
isPalindrome "haskell" = False
isPalindrome "madam" = True
```

