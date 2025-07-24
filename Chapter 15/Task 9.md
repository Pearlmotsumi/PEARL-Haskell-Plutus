HC15T9: Try Function for File IO Exceptions

---

### ✅ Full Haskell Example Using `try` for Safe File Reading

```haskell
import System.IO (readFile)
import Control.Exception (try, IOException)

main :: IO ()
main = do
    putStrLn "Enter the filename to read:"
    fileName <- getLine

    -- Try to read the file, catching IOExceptions
    result <- try (readFile fileName) :: IO (Either IOException String)

    case result of
        Right content -> putStrLn "File content:\n" >> putStrLn content
        Left ex       -> putStrLn $ "Failed to read the file: " ++ show ex
```

---

### 🔍 How It Works

* `try (readFile fileName)`: Attempts to read the file.
* `:: IO (Either IOException String)`: Explicitly sets the type so `try` knows what exception to catch.
* Pattern matches on the result:

  * `Right content`: Successfully read the file.
  * `Left ex`: An `IOException` occurred, e.g., file not found.

---

### 🧪 Example Run

**If the file exists:**

```
Enter the filename to read:
myfile.txt
File content:
Hello, this is the content of myfile.txt
```

**If the file doesn't exist:**

```
Enter the filename to read:
nofile.txt
Failed to read the file: myfile.txt: openFile: does not exist (No such file or directory)
```

---


