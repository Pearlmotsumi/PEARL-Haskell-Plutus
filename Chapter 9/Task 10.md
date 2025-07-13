HC9T10: Binary Search Tree Data Type

* Defines a **binary search tree** type `BST a`
* Uses two constructors:

  * `Empty` for an empty tree
  * `Node` for a value with left and right subtrees
* Includes an example tree and prints it in `main`

```haskell
-- Define the BST data type
data BST a = Empty
           | Node a (BST a) (BST a)
           deriving Show

-- Example BST:
--        10
--       /  \
--      5   15
--         /
--       12
exampleTree :: BST Int
exampleTree = Node 10
                (Node 5 Empty Empty)
                (Node 15
                    (Node 12 Empty Empty)
                    Empty)

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Example Binary Search Tree:"
  print exampleTree
```

### Sample Output:

```
Example Binary Search Tree:
Node 10 (Node 5 Empty Empty) (Node 15 (Node 12 Empty Empty) Empty)
```

