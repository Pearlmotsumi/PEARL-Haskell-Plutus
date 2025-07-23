HC12T7: Calculate Circle Area

```haskell
-- CircleArea.hs

calculateCircleArea :: Floating a => a -> a
calculateCircleArea radius = pi * radius ^ 2

main :: IO ()
main = do
  putStrLn "Enter the radius of the circle:"
  input <- getLine
  let radius = read input :: Double
      area = calculateCircleArea radius
  putStrLn ("The area of the circle is: " ++ show area)
```

---

### How to Run

1. Save the code as `CircleArea.hs`
2. Run it in GHCi:

```bash
ghci CircleArea.hs
*Main> main
```

Or compile and run:

```bash
ghc CircleArea.hs -o circlearea
./circlearea
```

---

### Example Interaction

```
Enter the radius of the circle:
3.5
The area of the circle is: 38.48451000647496
```


