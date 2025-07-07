HC1T5 - Task 5: Laziness in Haskell

* `infiniteNumbers`: an infinite list of natural numbers starting from 1
* `take n infiniteNumbers`: to extract the first `n` numbers
* A `main` function that demonstrates extracting the first 10 numbers.

```haskell
-- Define an infinite list of numbers starting from 1
infiniteNumbers :: [Int]
infiniteNumbers = [1..]

-- Main function to extract the first n numbers and print them
main :: IO ()
main = do
    let n = 10
    let firstN = take n infiniteNumbers
    putStrLn $ "First " ++ show n ++ " numbers from the infinite list:"
    print firstN
```

### Expected Output:

```haskell
First 10 numbers from the infinite list:
[1,2,3,4,5,6,7,8,9,10]
```

### How to Run:

1. Save as `InfiniteNumbers.hs`
2. Compile and run:

   ```bash
   ghc InfiniteNumbers.hs -o infiniteNumbers
   ./infiniteNumbers
   ```

