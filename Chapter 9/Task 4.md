HC9T4: Extract a Value from a Box

* Uses the `Box a` type
* Defines a function `extract` that returns the value inside a `Box`, or a default if the box is `Empty`
* Includes a `main` function that demonstrates both cases

```haskell
-- Define the Box data type
data Box a = Empty | Has a deriving Show

-- Function to extract the value from a Box or return a default
extract :: a -> Box a -> a
extract def Empty    = def
extract _   (Has x)  = x

-- Main function to run the code
main :: IO ()
main = do
  let box1 = Has 42
      box2 = Empty

      val1 = extract 0 box1
      val2 = extract 0 box2

  putStrLn "Extracting from box1 (Has 42):"
  print val1

  putStrLn "\nExtracting from box2 (Empty, default 0):"
  print val2
```

### Sample output:

```
Extracting from box1 (Has 42):
42

Extracting from box2 (Empty, default 0):
0
```


