HC13T1: List Files in Directory

```haskell
-- ListFiles.hs

import System.Directory (getCurrentDirectory, listDirectory)
import System.FilePath ((</>))
import Control.Monad (forM)

main :: IO ()
main = do
  -- Get the current working directory
  currentDir <- getCurrentDirectory
  putStrLn $ "Listing contents of: " ++ currentDir

  -- Get all entries (files and directories)
  entries <- listDirectory currentDir

  -- Print each entry
  putStrLn "Files and directories:"
  forM_ entries putStrLn
```

---

### 🔧 How to Run

1. Save this code as `ListFiles.hs`
2. Run in GHCi:

```bash
ghci ListFiles.hs
*Main> main
```

Or compile and run:

```bash
ghc ListFiles.hs -o listfiles
./listfiles
```

---

### ✅ Example Output

```
Listing contents of: /home/user/projects
Files and directories:
Main.hs
MathOperations.hs
data.txt
```

---

