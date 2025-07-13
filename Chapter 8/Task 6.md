HC8T6

* Defines a `Shape` type with two constructors: `Circle` and `Rectangle`, each using record syntax
* Creates one instance of each: a circle and a rectangle
* Prints both in the `main` function

```haskell
-- Define the Shape type with two constructors using record syntax
data Shape
  = Circle
      { center :: (Float, Float)
      , radius :: Float
      , color  :: String
      }
  | Rectangle
      { center :: (Float, Float)
      , width  :: Float
      , height :: Float
      , color  :: String
      }
  deriving Show

-- Create a circle instance
circle1 :: Shape
circle1 = Circle
  { center = (0.0, 0.0)
  , radius = 5.0
  , color  = "Red"
  }

-- Create a rectangle instance
rectangle1 :: Shape
rectangle1 = Rectangle
  { center = (10.0, 10.0)
  , width  = 8.0
  , height = 4.0
  , color  = "Blue"
  }

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Circle:"
  print circle1

  putStrLn "\nRectangle:"
  print rectangle1
```

### Sample Output:

```
Circle:
Circle {center = (0.0,0.0), radius = 5.0, color = "Red"}

Rectangle:
Rectangle {center = (10.0,10.0), width = 8.0, height = 4.0, color = "Blue"}
```

This example uses **distinct fields per constructor**, avoiding field name conflicts (like `color`) thanks to Haskell's support for shared names in separate constructors.

