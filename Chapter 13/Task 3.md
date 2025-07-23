HC13T3: Sort and Return Filtered Files

* **Reads files and directories** from the current directory
* **Filters** them using a substring provided by the user
* **Sorts** the result alphabetically using `Data.List.sort`
* Uses `Data.List.filter` and `Data.List.sort`

---

### ✅ Haskell Code: `SortedFilteredFiles.hs`

```haskell
-- SortedFilteredFiles.hs

import System.Directory (listDirectory, getCurrentDirectory)
import Data.List (filter, sort, isInfixOf)
import System.IO (hFlush, stdout)
import Control.Monad (forM_)

-- Function to filter and sort file names based on a substring
filterAndSortFiles :: String -> [FilePath] -> [FilePath]
filterAndSortFiles substring files =
  sort (filter (isInfixOf substring) files)

main :: IO ()
main = do
  putStr "Enter a substring to filter filenames: "
  hFlush stdout
  substring <- getLine

  currentDir <- getCurrentDirectory
  allFiles <- listDirectory currentDir

  let result = filterAndSortFiles substring allFiles

  putStrLn "\nFiltered and sorted files:"
  if null result
    then putStrLn "No matching files found."
    else forM_ result putStrLn
```

---

### 🔧 How to Run

1. Save the file as `SortedFilteredFiles.hs`
2. Run in GHCi:

```bash
ghci SortedFilteredFiles.hs
*Main> main
```

Or compile and run:

```bash
ghc SortedFilteredFiles.hs -o sortedfiles
./sortedfiles
```

---

### 🧪 Sample Output

```
Enter a substring to filter filenames: .hs

Filtered and sorted files:
FilterBySubstring.hs
Main.hs
SortedFilteredFiles.hs
```

---

