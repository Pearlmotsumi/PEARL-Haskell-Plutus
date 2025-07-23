HC13T8: Qualified Imports for Name Conflicts

---

### ✅ Full Example: `QualifiedImportsExample.hs`

```haskell
-- QualifiedImportsExample.hs

import qualified Data.Map as M
import qualified Data.List as L

-- A simple map of names to ages
peopleMap :: M.Map String Int
peopleMap = M.fromList [("Alice", 30), ("Bob", 25), ("Charlie", 35)]

-- A simple list of names
names :: [String]
names = ["Alice", "Bob", "Charlie", "Dave"]

main :: IO ()
main = do
  putStrLn "Using Data.List.filter to select names starting with 'C':"
  let cNames = L.filter (\name -> L.isPrefixOf "C" name) names
  print cNames

  putStrLn "\nUsing Data.Map.filter to select people older than 30:"
  let olderPeople = M.filter (> 30) peopleMap
  print olderPeople
```

---

### 🛠 How to Run

1. Save the code as `QualifiedImportsExample.hs`
2. Compile and run:

```bash
ghc QualifiedImportsExample.hs
./QualifiedImportsExample
```

---

### ✅ Output

```
Using Data.List.filter to select names starting with 'C':
["Charlie"]

Using Data.Map.filter to select people older than 30:
fromList [("Charlie",35)]
```

---

### 🔍 Why Use Qualified Imports?

Both `Data.List` and `Data.Map` define `filter`, so using `qualified`:

* Avoids **name collisions**
* Makes it clear which `filter` you mean: `L.filter` or `M.filter`

---

