HC8T10

* Defines a `Book` type using record syntax with fields `title`, `author`, and `year`
* Derives the `Show` instance automatically
* Creates a `Book` instance
* Prints it in the `main` function

```haskell
-- Define the Book type with deriving Show
data Book = Book
  { title  :: String
  , author :: String
  , year   :: Int
  } deriving Show

-- Create an instance of Book
myBook :: Book
myBook = Book
  { title = "The Hobbit"
  , author = "J.R.R. Tolkien"
  , year = 1937
  }

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Book details:"
  print myBook
```

### Sample output:

```
Book details:
Book {title = "The Hobbit", author = "J.R.R. Tolkien", year = 1937}
```


