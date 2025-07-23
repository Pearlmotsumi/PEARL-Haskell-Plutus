HC12T6: Sort a List of Integers

* Reads a list of integers from the user (entered as space-separated numbers in a single line)
* Sorts the list in ascending order
* Prints the sorted list

```haskell
-- SortList.hs

import Data.List (sort)

main :: IO ()
main = do
  putStrLn "Enter a list of integers separated by spaces:"
  input <- getLine
  let numbers = map read (words input) :: [Int]
      sortedNumbers = sort numbers
  putStrLn ("Sorted list: " ++ show sortedNumbers)
```

---

### How to Run

1. Save the code as `SortList.hs`
2. Run it in GHCi:

```bash
ghci SortList.hs
*Main> main
```

Or compile and run:

```bash
ghc SortList.hs -o sortlist
./sortlist
```

---

### Example Interaction

```
Enter a list of integers separated by spaces:
4 2 7 1 5
Sorted list: [1,2,4,5,7]
```


