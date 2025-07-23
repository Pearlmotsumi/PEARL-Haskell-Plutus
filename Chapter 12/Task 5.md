HC12T5: Palindrome Checker

```haskell
-- Palindrome.hs

import Data.Char (toLower, isAlphaNum)

-- Checks if a string is a palindrome ignoring case and non-alphanumeric characters
isPalindrome :: String -> Bool
isPalindrome s = cleaned == reverse cleaned
  where
    cleaned = map toLower (filter isAlphaNum s)

main :: IO ()
main = do
  putStrLn "Enter a string to check if it is a palindrome:"
  input <- getLine
  if isPalindrome input
    then putStrLn "It is a palindrome."
    else putStrLn "It is not a palindrome."
```

---

### How It Works

* `isPalindrome` first cleans the string by converting to lowercase and removing non-alphanumeric characters.
* It then compares the cleaned string to its reverse.

---

### How to Run

1. Save as `Palindrome.hs`
2. Run in GHCi:

```bash
ghci Palindrome.hs
*Main> main
```

Or compile and run:

```bash
ghc Palindrome.hs -o palindrome
./palindrome
```

---

### Example Interaction

```
Enter a string to check if it is a palindrome:
A man, a plan, a canal, Panama!
It is a palindrome.
```


