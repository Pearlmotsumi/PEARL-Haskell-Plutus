HC13T2: Filter Files by Substring

* Uses `Data.List.isInfixOf` to filter files and directories in the current directory based on a **user-provided substring**
* Uses `System.Directory.listDirectory` to get the contents of the current directory
* Uses `main` to tie it all together

---

### ✅ Haskell Code: `FilterBySubstring.hs`

```haskell
-- FilterBySubstring.hs

import System.Directory (listDirectory, getCurrentDirectory)
import Data.List (isInfixOf)
import System.IO (hFlush, stdout)
import Control.Monad (forM_)

-- Function to filter file names based on a substring
filterFilesBySubstring :: String -> [FilePath] -> [FilePath]
filterFilesBySubstring substring = filter (isInfixOf substring)

main :: IO ()
main = do
  putStr "Enter a substring to filter filenames: "
  hFlush stdout
  substring <- getLine

  currentDir <- getCurrentDirectory
  allFiles <- listDirectory currentDir

  let matchingFiles = filterFilesBySubstring substring allFiles

  putStrLn "\nMatching files:"
  if null matchingFiles
    then putStrLn "No matching files found."
    else forM_ matchingFiles putStrLn
```

---

### 🔧 How to Run

1. Save the file as `FilterBySubstring.hs`
2. Run in GHCi:

```bash
ghci FilterBySubstring.hs
*Main> main
```

Or compile it:

```bash
ghc FilterBySubstring.hs -o filterfiles
./filterfiles
```

---

### 🧪 Sample Output

```
Enter a substring to filter filenames: .hs

Matching files:
Main.hs
FilterBySubstring.hs
Utils.hs
```

---

