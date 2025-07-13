HC9T8: Define a Recursive Sequence Data Type

* Defines a **recursive data type** `Sequence a`, which is a linear chain of nodes
* Each node contains a value of type `a` and points to the next node
* Includes a constructor for the end of the sequence (`Empty`)
* Demonstrates how to construct and print a sequence in `main`

```haskell
-- Define the recursive Sequence data type
data Sequence a = Empty | Node a (Sequence a) deriving Show

-- Example sequence: 1 -> 2 -> 3 -> Empty
exampleSeq :: Sequence Int
exampleSeq = Node 1 (Node 2 (Node 3 Empty))

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Linear sequence of integers:"
  print exampleSeq
```

### Sample Output:

```
Linear sequence of integers:
Node 1 (Node 2 (Node 3 Empty))
```

### Optional:

