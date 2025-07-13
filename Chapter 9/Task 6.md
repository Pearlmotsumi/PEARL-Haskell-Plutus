HC9T6: Define a Recursive Data Type

* A tweet has:

  * `content :: String`
  * `likes :: Int`
  * `comments :: [Tweet]` — which are themselves tweets
* Includes a sample tweet with nested replies (comments)
* Prints it using the `Show` instance

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving Show

-- Example tweets
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
  putStrLn "Tweet thread:"
  print mainTweet
```

### Sample Output (simplified):

```
Tweet thread:
Tweet {content = "Learning Haskell is fun!", likes = 120, comments = [Tweet {content = "Absolutely agree!", likes = 15, comments = []},Tweet {content = "Try monads next 😄", likes = 22, comments = [Tweet {content = "That's the scary part 😅", likes = 5, comments = []}]}]}
```

