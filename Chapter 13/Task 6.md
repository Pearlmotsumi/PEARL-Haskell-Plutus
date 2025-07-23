HC13T6: File Names to Map

* Reads all file and directory names in the current directory
* Filters them by a user-specified **substring**
* Converts the filtered list into a **key-value map** using `Data.Map`

  * The **key** is the file name
  * The **value** is the length of the file name (or any metadata you want)
* Uses `Data.Map.fromList`

---

### ✅ Full Code: `FileMap.hs`

```haskell
-- FileMap.hs

import System.Directory (listDirectory, getCurrentDirectory)
import Data.List (isInfixOf)
import qualified Data.Map as Map
import System.IO (hFlush, stdout)

-- Function to filter filenames by a substring
filterFiles :: String -> [FilePath] -> [FilePath]
filterFiles substring = filter (isInfixOf substring)

-- Convert list of file names to a Map with file name -> length
filesToMap :: [FilePath] -> Map.Map FilePath Int
filesToMap files = Map.fromList [(file, length file) | file <- files]

main :: IO ()
main = do
  putStr "Enter a substring to filter file names: "
  hFlush stdout
  substring <- getLine

  currentDir <- getCurrentDirectory
  files <- listDirectory currentDir
  let filtered = filterFiles substring files
  let fileMap = filesToMap filtered

  putStrLn "\nFiltered File Map (FileName -> Length):"
  if Map.null fileMap
    then putStrLn "No matching files found."
    else mapM_ print (Map.toList fileMap)
```

---

### 🧪 Example Run

```
Enter a substring to filter file names: .hs

Filtered File Map (FileName -> Length):
("Main.hs",7)
("FileMap.hs",10)
("Utilities.hs",13)
```

---

### 🛠 How to Run

1. Save the code as `FileMap.hs`
2. Compile and run it:

```bash
ghc FileMap.hs
./FileMap
```

---

