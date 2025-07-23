HC12T1: Print a Welcome Message

```haskell
-- Welcome.hs

main :: IO ()
main = putStrLn "Welcome to Haskell Programming!"
```

---

### How to Run

1. Save the code as `Welcome.hs`
2. Run it in GHCi:

```bash
ghci Welcome.hs
*Main> main
```

Or compile and run:

```bash
ghc Welcome.hs -o welcome
./welcome
```

---

It will output:

```
Welcome to Haskell Programming!
```

