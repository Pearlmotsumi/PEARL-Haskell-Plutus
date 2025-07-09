HC7T4: Create a custom type and implement Show and Read

```haskell
import Text.Read (readMaybe)

-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double

-- Implement Show instance for Shape
instance Show Shape where
    show (Circle r) = "Circle " ++ show r
    show (Rectangle w h) = "Rectangle " ++ show w ++ " " ++ show h

-- Implement Read instance for Shape
instance Read Shape where
    readsPrec _ input =
        case words input of
            ("Circle":rStr:rest) ->
                case reads rStr of
                    [(r, "")] -> [(Circle r, unwords rest)]
                    _         -> []
            ("Rectangle":wStr:hStr:rest) ->
                case (reads wStr, reads hStr) of
                    ([(w, "")], [(h, "")]) -> [(Rectangle w h, unwords rest)]
                    _                      -> []
            _ -> []

-- Main function to test Show and Read
main :: IO ()
main = do
    let c = Circle 5.0
        r = Rectangle 3.0 4.0

    -- Show examples
    putStrLn $ "Show Circle: " ++ show c
    putStrLn $ "Show Rectangle: " ++ show r

    -- Read examples
    let s1 = readMaybe "Circle 10.5" :: Maybe Shape
        s2 = readMaybe "Rectangle 6.2 7.3" :: Maybe Shape
        s3 = readMaybe "Rectangle 6.2" :: Maybe Shape  -- Should fail

    print s1
    print s2
    print s3
```

---

### How to run

1. Save as `ShapeReadShow.hs`
2. Compile and run:

```bash
ghc ShapeReadShow.hs -o shapetest
./shapetest
```

---

### Expected output

```
Show Circle: Circle 5.0
Show Rectangle: Rectangle 3.0 4.0
Just (Circle 10.5)
Just (Rectangle 6.2 7.3)
Nothing
```


