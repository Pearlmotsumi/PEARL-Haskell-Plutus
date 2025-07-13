HC9T7: Implement a Function to Calculate Engagement

* Uses the `Tweet` type (recursive)
* Defines a function `engagement :: Tweet -> Int` that calculates the total engagement by summing:

  * The tweet’s own likes
  * The engagement of all its comments recursively
* Includes a `main` function to test it

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving Show

-- Function to calculate total engagement (likes + nested comment likes)
engagement :: Tweet -> Int
engagement (Tweet _ l cs) = l + sum (map engagement cs)

-- Example tweet thread
mainTweet :: Tweet
mainTweet = Tweet
  { content = "Learning Haskell is fun!"
  , likes = 120
  , comments =
      [ Tweet
          { content = "Absolutely agree!"
          , likes = 15
          , comments = []
          }
      , Tweet
          { content = "Try monads next 😄"
          , likes = 22
          , comments =
              [ Tweet
                  { content = "That's the scary part 😅"
                  , likes = 5
                  , comments = []
                  }
              ]
          }
      ]
  }

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Main tweet engagement total:"
  print (engagement mainTweet)
```

### Sample Output:

```
Main tweet engagement total:
162
```

> **Explanation**:

* `120` (main tweet)
* `15` (first comment)
* `22` (second comment)
* `5` (nested comment)
* **Total: 120 + 15 + 22 + 5 = 162**


