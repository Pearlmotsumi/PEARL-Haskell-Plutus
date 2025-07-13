HC9T3: Define a Function to Add Values in a Box

* Uses the previously defined `Box a` type
* Defines a function `addN` which takes a number and a `Box a`
* Adds the number to the value inside the box if it contains a number (`Has a`), otherwise returns `Empty`
* Includes a `main` function to demonstrate usage with `Box Int`

```haskell
-- Define the Box data type
data Box a = Empty | Has a deriving Show

-- Function to add n to the content of the box if it's there
addN :: Num a => a -> Box a -> Box a
addN _ Empty    = Empty
addN n (Has x)  = Has (x + n)

-- Main function to run the code
main :: IO ()
main = do
  let box1 = Has 10
      box2 = Empty
      result1 = addN 5 box1
      result2 = addN 5 box2

  putStrLn "Adding 5 to box1:"
  print result1

  putStrLn "Adding 5 to box2:"
  print result2
```

### Sample output:

```
Adding 5 to box1:
Has 15

Adding 5 to box2:
Empty
```


