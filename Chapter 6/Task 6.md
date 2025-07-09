HC6T6

```haskell
-- Recursive function to check if an element exists in a list
elementExists :: Eq a => a -> [a] -> Bool
elementExists _ [] = False
elementExists e (x:xs)
    | e == x    = True
    | otherwise = elementExists e xs

-- Main function to test elementExists
main :: IO ()
main = do
    print $ elementExists 3 [1, 2, 3, 4, 5]    -- True
    print $ elementExists 'a' "haskell"        -- True
    print $ elementExists 10 [1, 2, 3]         -- False
    print $ elementExists 'z' "hello world"    -- False
```

---

### How to run

1. Save the code in a file, e.g., `ElementExists.hs`
2. Compile and run:

```bash
ghc ElementExists.hs -o elementexists
./elementexists
```

---

### Expected output

```
True
True
False
False
```
