HC12T9: Read and Print File Content

```haskell
-- ReadFile.hs

import System.IO (hPutStrLn, stderr)
import Control.Exception (catch, IOException)

main :: IO ()
main = do
  putStrLn "Enter the filename to read:"
  filename <- getLine
  content <- safeReadFile filename
  case content of
    Just text -> putStrLn "\nFile content:\n" >> putStrLn text
    Nothing   -> hPutStrLn stderr "Error: Could not read the file. Please check if the file exists."

safeReadFile :: FilePath -> IO (Maybe String)
safeReadFile path = catch (Just <$> readFile path) handleReadError
  where
    handleReadError :: IOException -> IO (Maybe String)
    handleReadError _ = return Nothing
```

---

### How to Run

1. Save the code as `ReadFile.hs`
2. Run it in GHCi:

```bash
ghci ReadFile.hs
*Main> main
```

Or compile and run:

```bash
ghc ReadFile.hs -o readfile
./readfile
```

---

### Sample interaction

```
Enter the filename to read:
example.txt

File content:
This is the content of example.txt.
```

If the file does not exist or cannot be read, it prints an error message to `stderr` instead.

