HC9T5: Create a Parametric Data Type with Record Syntax

* Defines a **parametric data type** `Shape a` with two constructors: `Circle` and `Rectangle`
* Each constructor includes a `color :: a` field (the parameterized type)
* Demonstrates how to create `Shape` instances using different types for color (like `String` and `Int`)
* Prints the shapes using the derived `Show` instance

```haskell
-- Define the parametric data type Shape a
data Shape a
  = Circle { radius :: Float, color :: a }
  | Rectangle { width :: Float, height :: Float, color :: a }
  deriving Show

-- Main function to run the code
main :: IO ()
main = do
  -- Shape with color as String
  let redCircle = Circle { radius = 5.0, color = "Red" }

  -- Shape with color as Int (e.g., color code)
  let codedRectangle = Rectangle { width = 4.0, height = 3.0, color = 255 }

  putStrLn "Circle with String color:"
  print redCircle

  putStrLn "\nRectangle with Int color code:"
  print codedRectangle
```

### Sample Output:

```
Circle with String color:
Circle {radius = 5.0, color = "Red"}

Rectangle with Int color code:
Rectangle {width = 4.0, height = 3.0, color = 255}
```

This setup allows you to use `Shape String`, `Shape Int`, or any other type for `color`, giving flexibility to the `Shape` representation.

