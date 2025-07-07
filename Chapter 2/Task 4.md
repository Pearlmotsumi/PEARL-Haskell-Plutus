HC2T4 - Task 4: Converting Between Infix and Prefix Notations

```haskell
module Main where

main :: IO ()
main = do
    -- Infix to prefix
    let prefixAdd = (+) 5 3
    let prefixMul = (*) 10 4
    let prefixAnd = (&&) True False

    putStrLn $ "Prefix notation (+) 5 3 = " ++ show prefixAdd
    putStrLn $ "Prefix notation (*) 10 4 = " ++ show prefixMul
    putStrLn $ "Prefix notation (&&) True False = " ++ show prefixAnd

    -- Prefix to infix
    let infixAdd = 7 + 2
    let infixMul = 6 * 5
    let infixAnd = True && False

    putStrLn $ "Infix notation 7 + 2 = " ++ show infixAdd
    putStrLn $ "Infix notation 6 * 5 = " ++ show infixMul
    putStrLn $ "Infix notation True && False = " ++ show infixAnd
```

### Explanation:

* Prefix notation uses parentheses with the operator first, e.g. `(+) 5 3`
* Infix notation uses the operator between operands, e.g. `5 + 3`

Running this program will output:

```
Prefix notation (+) 5 3 = 8
Prefix notation (*) 10 4 = 40
Prefix notation (&&) True False = False
Infix notation 7 + 2 = 9
Infix notation 6 * 5 = 30
Infix notation True && False = False
```


