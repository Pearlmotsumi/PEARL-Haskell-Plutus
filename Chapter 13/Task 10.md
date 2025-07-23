HC13T10: Multi-Module Main Function

* Lists all files/directories in the current directory (`System.Directory.listDirectory`)
* Filters the files whose names contain a user-given substring (`Data.List.isInfixOf`)
* Sorts the filtered file list (`Data.List.sort`)
* Prints the sorted filtered list

---

```haskell
-- SearchAndSortFiles.hs

import System.Directory (listDirectory, getCurrentDirectory)
import Data.List (isInfixOf, sort)
import System.IO (hFlush, stdout)

main :: IO ()
main = do
  putStr "Enter substring to search for in file names: "
  hFlush stdout
  substring <- getLine

  currentDir <- getCurrentDirectory
  allFiles <- listDirectory currentDir

  let filteredFiles = filter (isInfixOf substring) allFiles
      sortedFiles = sort filteredFiles

  putStrLn "\nSorted matching files:"
  if null sortedFiles
    then putStrLn "No files matched the substring."
    else mapM_ putStrLn sortedFiles
```

---

### How to run

1. Save as `SearchAndSortFiles.hs`
2. Compile and run:

```bash
ghc SearchAndSortFiles.hs -o searchfiles
./searchfiles
```

Or run in GHCi:

```bash
ghci SearchAndSortFiles.hs
*Main> main
```

---

### Sample interaction

```
Enter substring to search for in file names: hs

Sorted matching files:
Main.hs
SearchAndSortFiles.hs
Utils.hs
```

---


