HC1T1 - Task 1: Function Composition

-- double: Multiplies a number by 2
double :: Int -> Int
double x = x * 2

-- increment: Increases a number by 1
increment :: Int -> Int
increment x = x + 1

-- doubleThenIncrement: Applies double first, then increment using function composition
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double

-- main: Runs the function on a sample number and prints the result
main :: IO ()
main = do
    let input = 5
    let result = doubleThenIncrement input
    putStrLn $ "Result of doubleThenIncrement " ++ show input ++ " is: " ++ show result
