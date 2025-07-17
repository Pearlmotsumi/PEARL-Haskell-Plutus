HC10T5: ShowDetailed Type Class

1. Define a **type class** `ShowDetailed` with a function `showDetailed :: a -> String`.
2. Create a **`User` data type** with fields for name and age.
3. Provide an **instance of `ShowDetailed`** for the `User` type.

---

### ✅ Haskell Code

```haskell
-- Define the type class ShowDetailed
class ShowDetailed a where
  showDetailed :: a -> String

-- Define a User type
data User = User
  { name :: String
  , age  :: Int
  }

-- Implement ShowDetailed for User
instance ShowDetailed User where
  showDetailed (User n a) = "User: " ++ n ++ ", Age: " ++ show a

-- Main function to demonstrate showDetailed
main :: IO ()
main = do
  let user1 = User "Alice" 30
  let user2 = User "Bob" 22

  putStrLn (showDetailed user1)
  putStrLn (showDetailed user2)
```

---

### 🟢 Sample Output

```
User: Alice, Age: 30
User: Bob, Age: 22
```

