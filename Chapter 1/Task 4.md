HC1T4 - Task 4: Composing a Function to Process Player Data

* `extractPlayers`: gets names from a list of `(name, score)` pairs
* `sortByScore`: sorts by score in descending order
* `topThree`: returns the top 3 entries from a list
* `getTopThreePlayers`: composes the above functions to return the top 3 player names

```haskell
import Data.List (sortBy)
import Data.Ord (comparing)

-- Extract player names from (name, score) tuples
extractPlayers :: [(String, Int)] -> [String]
extractPlayers players = map fst players

-- Sort the list of (name, score) tuples by score in descending order
sortByScore :: [(String, Int)] -> [(String, Int)]
sortByScore players = sortBy (flip (comparing snd)) players

-- Get the top three players (after sorting)
topThree :: [(String, Int)] -> [(String, Int)]
topThree players = take 3 players

-- Compose everything to get top 3 player names
getTopThreePlayers :: [(String, Int)] -> [String]
getTopThreePlayers = extractPlayers . topThree . sortByScore

-- Main function to test everything
main :: IO ()
main = do
    let players = [("Alice", 45), ("Bob", 67), ("Charlie", 53), ("Diana", 88), ("Eve", 32)]
    putStrLn "Top three players:"
    print (getTopThreePlayers players)
```

### Expected Output:

```haskell
Top three players:
["Diana","Bob","Charlie"]
```

### How to Run:

1. Save this as `TopThreePlayers.hs`
2. Compile and run:

   ```bash
   ghc TopThreePlayers.hs -o topThreePlayers
   ./topThreePlayers
   ```

