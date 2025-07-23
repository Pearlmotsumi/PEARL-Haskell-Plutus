HC14T8: Character Frequency Function

---

### ✅ Full Haskell Example

```haskell
import Data.List (group, sort)

-- Count character frequencies
counts :: String -> [(Char, Int)]
counts str = map (\g -> (head g, length g)) . group . sort $ str

main :: IO ()
main = do
    putStrLn "Enter a string:"
    input <- getLine
    let freq = counts input
    putStrLn "Character frequencies:"
    print freq
```

---

### ✅ How It Works

* `sort str` arranges characters in order.
* `group` clusters identical characters together.
* `map (\g -> (head g, length g))` creates a tuple for each group: `(character, count)`.

---

### 🧪 Sample Run

```
Enter a string:
hello world
Character frequencies:
[(' ',1),('d',1),('e',1),('h',1),('l',3),('o',2),('r',1),('w',1)]
```


