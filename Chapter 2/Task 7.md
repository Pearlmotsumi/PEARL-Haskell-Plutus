HC2T7 - Task 7: Boolean Expressions

```haskell
module Main where

main :: IO ()
main = do
    -- True using &&
    let expr1 = True && True

    -- False using ||
    let expr2 = False || False

    -- True using not
    let expr3 = not False

    -- A comparison that returns False
    let expr4 = 5 > 10

    putStrLn $ "True using &&: " ++ show expr1
    putStrLn $ "False using ||: " ++ show expr2
    putStrLn $ "True using not: " ++ show expr3
    putStrLn $ "Comparison that returns False (5 > 10): " ++ show expr4
```

### What this does:

* `expr1` uses `&&` to get `True`
* `expr2` uses `||` to get `False`
* `expr3` uses `not` to get `True`
* `expr4` uses a comparison that evaluates to `False`

Running this will output:

```
True using &&: True
False using ||: False
True using not: True
Comparison that returns False (5 > 10): False
```

