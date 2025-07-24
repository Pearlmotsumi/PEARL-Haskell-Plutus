HC16T10: Character Frequency in String

---

### ✅ Haskell Code: Character Frequency Counter

```haskell
import Data.List (group, sort)

-- Function to count character frequencies
charFrequencies :: String -> [(Char, Int)]
charFrequencies str = map (\cs -> (head cs, length cs)) . group . sort $ str

-- Main function to demonstrate usage
main :: IO ()
main = do
    putStrLn "Enter a string:"
    input <- getLine
    let freqs = charFrequencies input
    putStrLn "Character frequencies:"
    mapM_ print freqs
```

---

### 🧪 Example Run

```
Enter a string:
hello world
Character frequencies:
(' ',1)
('d',1)
('e',1)
('h',1)
('l',3)
('o',2)
('r',1)
('w',1)
```

---

### 🔧 Notes

* The `group` function groups equal adjacent characters — that's why we sort first.
* The frequency result is a list of tuples `(Char, Int)`.
* This approach includes spaces and punctuation; filter them out if needed.


