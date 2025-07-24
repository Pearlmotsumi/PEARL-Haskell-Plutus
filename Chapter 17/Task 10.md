HC17T10: Monoid Instance for Config

* Lowest loggingLevel (`0`)
* Highest timeout (`maxBound :: Int`)
* Lowest retries (`0`)

The `main` function demonstrates combining configs including the identity.

---

### ✅ Haskell Code: `Config` with `Semigroup` and `Monoid` Instances

```haskell
import Data.Semigroup (Semigroup(..))
import Data.Monoid (Monoid(..))
import Data.Int (maxBound)

-- Define Config data type
data Config = Config
  { loggingLevel :: Int
  , timeout      :: Int
  , retries      :: Int
  } deriving (Show, Eq)

-- Semigroup instance for Config
instance Semigroup Config where
  c1 <> c2 = Config
    { loggingLevel = max (loggingLevel c1) (loggingLevel c2)
    , timeout      = min (timeout c1)      (timeout c2)
    , retries      = max (retries c1)      (retries c2)
    }

-- Monoid instance for Config
instance Monoid Config where
  mempty = Config
    { loggingLevel = 0
    , timeout      = maxBound
    , retries      = 0
    }
  mappend = (<>)

-- Main to demonstrate Monoid behavior
main :: IO ()
main = do
  let config1 = Config { loggingLevel = 3, timeout = 60, retries = 2 }
      config2 = Config { loggingLevel = 5, timeout = 30, retries = 4 }
      combined = config1 <> config2
      combinedWithIdentity = combined <> mempty

  putStrLn "Config 1:"
  print config1
  putStrLn "Config 2:"
  print config2
  putStrLn "Combined Config:"
  print combined
  putStrLn "Combined with mempty:"
  print combinedWithIdentity
```

---

### 🧪 Example Output

```
Config 1:
Config {loggingLevel = 3, timeout = 60, retries = 2}
Config 2:
Config {loggingLevel = 5, timeout = 30, retries = 4}
Combined Config:
Config {loggingLevel = 5, timeout = 30, retries = 4}
Combined with mempty:
Config {loggingLevel = 5, timeout = 30, retries = 4}
```

---

### 🔍 Explanation

* `mempty` represents a default config with minimal logging, maximal timeout, and zero retries.
* Combining any config with `mempty` leaves it unchanged.


