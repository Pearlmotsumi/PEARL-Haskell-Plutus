HC1T3 - Task 3: Checking if a Number is Greater than 18

-- greaterThan18: Checks if the given number is greater than 18
greaterThan18 :: Int -> Bool
greaterThan18 number = number > 18

-- main: Tests the greaterThan18 function with some example values
main :: IO ()
main = do
    let num1 = 15
    let num2
