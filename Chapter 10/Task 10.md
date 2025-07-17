HC10T10: Concatenatable Type Class

* Defines a type class `Concatenatable` with a function `concatWith :: a -> a -> a`
* Implements it for the type `[Char]` (which is `String`)
* Demonstrates usage in `main`

---

### ✅ Haskell Code

```haskell
-- Define the Concatenatable type class
class Concatenatable a where
  concatWith :: a -> a -> a

-- Implement Concatenatable for String ([Char])
instance Concatenatable [Char] where
  concatWith = (++)

-- Main function to demonstrate usage
main :: IO ()
main = do
  let str1 = "Hello, "
  let str2 = "World!"
  putStrLn $ concatWith str1 str2  -- Output: Hello, World!
```

---

### 🟢 Sample Output

```
Hello, World!
```

---

