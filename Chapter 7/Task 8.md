HC7T8: Use Read to parse a value from a string

```haskell
import Text.Read (readMaybe)

-- Define Shape data type
data Shape = Circle Double | Rectangle Double Double
    deriving (Show, Eq)

-- Parse a Shape from a string safely
parseShape :: String -> Maybe Shape
parseShape input = case words input of
    ("Circle":rStr:[]) ->
        case readMaybe rStr of
            Just r  -> Just (Circle r)
            Nothing -> Nothing
    ("Rectangle":wStr:hStr:[]) ->
        case (readMaybe wStr, readMaybe hStr) of
            (Just w, Just h) -> Just (Rectangle w h)
            _                -> Nothing
    _ -> Nothing

-- Main function to test parseShape
main :: IO ()
main = do
    print $ parseShape "Circle 5.0"        -- Just (Circle 5.0)
    print $ parseShape "Rectangle 3 4"     -- Just (Rectangle 3.0 4.0)
    print $ parseShape "Rectangle 3"       -- Nothing
    print $ parseShape "Square 5"           -- Nothing
    print $ parseShape "Circle abc"         -- Nothing
```

---

### How to run

1. Save as `ParseShape.hs`
2. Compile and run:

```bash
ghc ParseShape.hs -o parshape
./parshape
```

---

### Expected output

```
Just (Circle 5.0)
Just (Rectangle 3.0 4.0)
Nothing
Nothing
Nothing
```


