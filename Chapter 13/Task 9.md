HC13T9: Renaming Module Namespace

```haskell
-- RenamedModulesExample.hs

import qualified Data.Map as DM
import qualified Data.List as DL

main :: IO ()
main = do
  let myMap = DM.fromList [("apple", 3), ("banana", 5), ("cherry", 2)]
      myList = ["banana", "apple", "date", "cherry"]

  putStrLn "Original Map:"
  print myMap

  putStrLn "\nOriginal List:"
  print myList

  -- Use DM.filter to keep entries with value > 2
  let filteredMap = DM.filter (> 2) myMap
  putStrLn "\nFiltered Map (values > 2):"
  print filteredMap

  -- Use DL.sort to sort the list
  let sortedList = DL.sort myList
  putStrLn "\nSorted List:"
  print sortedList
```

---

### How to Run

1. Save as `RenamedModulesExample.hs`
2. Run in GHCi or compile:

```bash
ghc RenamedModulesExample.hs
./RenamedModulesExample
```

---

### Output Example

```
Original Map:
fromList [("apple",3),("banana",5),("cherry",2)]

Original List:
["banana","apple","date","cherry"]

Filtered Map (values > 2):
fromList [("apple",3),("banana",5)]

Sorted List:
["apple","banana","cherry","date"]
```

---

This shows how to:

* Rename imports with `as` (e.g., `Data.Map` → `DM`, `Data.List` → `DL`)
* Use functions from both modules clearly with the aliases


