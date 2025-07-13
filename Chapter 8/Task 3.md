HC8T3

* Defines a `Shape` data type with `Circle` and `Rectangle` constructors
* Implements an `area` function to compute the area
* Calculates the area of a circle with radius 5 and a rectangle with sides 10 and 5
* Includes a `main` function to run and display the results

```haskell
-- Define the Shape data type
data Shape = Circle Float | Rectangle Float Float deriving Show

-- Function to calculate the area of a shape
area :: Shape -> Float
area (Circle r) = pi * r * r
area (Rectangle l w) = l * w

-- Main function to run the code
main :: IO ()
main = do
  let circle = Circle 5
  let rectangle = Rectangle 10 5
  putStrLn $ "Area of the circle with radius 5: " ++ show (area circle)
  putStrLn $ "Area of the rectangle with sides 10 and 5: " ++ show (area rectangle)
```

### Sample output when run:

```
Area of the circle with radius 5: 78.53982
Area of the rectangle with sides 10 and 5: 50.0
```


