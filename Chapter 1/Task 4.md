HC1T4 - Task 4: Composing a Function to Process Player Data

-- extractPlayers: Extracts the player names from a list of tuples (name, score)
extractPlayers :: [(String, Int)] -> [String]
extractPlayers = map fst  -- `fst` extracts the first element (name) of each tuple

-- sortByScore: Sorts the list of players by score in descending order
sortByScore :: [(String, Int)] -> [(String, Int)]
sortByScore = reverse . sortBy (compare `on` snd)  -- `snd` extracts the second eleme
