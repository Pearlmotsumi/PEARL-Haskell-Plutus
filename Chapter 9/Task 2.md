HC9T2: Implement a Parametric Data Type

* Defines a parametric data type `Box a` with constructors `Empty` and `Has a`
* Demonstrates usage by creating empty and non-empty boxes
* Prints the boxes in the `main` function

```haskell
-- Define the Box data type
data Box a = Empty | Has a deriving Show

-- Example boxes
emptyBox :: Box Int
emptyBox = Empty

fullBox :: Box String
fullBox = Has "Surprise!"

-- Main function
main :: IO ()
main = do
  putStrLn "Empty box:"
  print emptyBox

  putStrLn "\nFull box:"
  print fullBox
```

### Sample output:

```
Empty box:
Empty

Full box:
Has "Surprise!"
```

