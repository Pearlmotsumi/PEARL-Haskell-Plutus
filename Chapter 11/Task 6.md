HC11T6: Uppercase Converter

1. Reads a line of input from the user
2. Converts it to **uppercase**
3. Prints the result

```haskell
-- ToUppercase.hs

import Data.Char (toUpper)

main :: IO ()
main = do
  putStrLn "Enter a line of text:"
  input <- getLine
  let upperInput = map toUpper input
  putStrLn ("Uppercase: " ++ upperInput)
```

### How It Works

* `getLine` reads input from the user
* `map toUpper` converts each character to uppercase
* `putStrLn` prints the transformed string

### How to Run

1. Save this as `ToUppercase.hs`
2. In terminal, run it with:

```bash
ghci ToUppercase.hs
*Main> main
```

Or compile:

```bash
ghc ToUppercase.hs -o toupper
./toupper
```

### Example Interaction

```
Enter a line of text:
Haskell is fun!
Uppercase: HASKELL IS FUN!
```


