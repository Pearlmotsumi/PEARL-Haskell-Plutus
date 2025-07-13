HC9T9: Check for Element in a Sequence

* Uses the previously defined `Sequence a` recursive data type
* Implements the function `elemSeq :: Eq a => a -> Sequence a -> Bool` to check if an element exists in the sequence
* Demonstrates usage in `main`

```haskell
-- Define the recursive Sequence data type
data Sequence a = Empty | Node a (Sequence a) deriving Show

-- Function to check if an element exists in the sequence
elemSeq :: Eq a => a -> Sequence a -> Bool
elemSeq _ Empty = False
elemSeq x (Node y rest)
  | x == y    = True
  | otherwise = elemSeq x rest

-- Example sequence: 1 -> 2 -> 3 -> Empty
exampleSeq :: Sequence Int
exampleSeq = Node 1 (Node 2 (Node 3 Empty))

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Checking if 2 is in the sequence:"
  print (elemSeq 2 exampleSeq)

  putStrLn "Checking if 5 is in the sequence:"
  print (elemSeq 5 exampleSeq)
```

### Sample Output:

```
Checking if 2 is in the sequence:
True

Checking if 5 is in the sequence:
False
```


