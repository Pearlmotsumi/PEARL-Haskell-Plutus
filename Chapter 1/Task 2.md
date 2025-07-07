HC1T2 - Task 2: Pure Function Example

-- Importing the math library for Pi
import Prelude (Float, (*), pi)

-- circleArea: Calculates the area of a circle given the radius
circleArea :: Float -> Float
circleArea radius = pi * radius * radius

-- main: Runs the circleArea function on a sample radius and prints the result
main :: IO ()
main = do
    let radius = 5.0
    let area = circleArea radius
