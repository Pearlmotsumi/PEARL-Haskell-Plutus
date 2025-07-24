HC17T9: Config Data Type and Semigroup Instance

* Maximum of `loggingLevel`
* Minimum of `timeout`
* Maximum of `retries`

The `main` function demonstrates combining two sample configs.

---

### ✅ Haskell Code: `Config` with Semigroup Instance

```haskell
import Data.Semigroup (Semigroup(..))

-- Define a Config data type
data Config = Config
  { loggingLevel :: Int  -- e.g., 0=none, higher = more verbose
  , timeout      :: Int  -- in seconds
  , retries      :: Int
  } deriving (Show, Eq)

-- Semigroup instance for Config
instance Semigroup Config where
  c1 <> c2 = Config
    { loggingLevel = max (loggingLevel c1) (loggingLevel c2)
    , timeout      = min (timeout c1)      (timeout c2)
    , retries      = max (retries c1)      (retries c2)
    }

-- Main to demonstrate combining Configs
main :: IO ()
main = do
  let config1 = Config { loggingLevel = 2, timeout = 30, retries = 3 }
      config2 = Config { loggingLevel = 5, timeout = 20, retries = 1 }

  let combined = config1 <> config2

  putStrLn "Config 1:"
  print config1
  putStrLn "Config 2:"
  print config2
  putStrLn "Combined Config:"
  print combined
```

---

### 🧪 Example Output

```
Config 1:
Config {loggingLevel = 2, timeout = 30, retries = 3}
Config 2:
Config {loggingLevel = 5, timeout = 20, retries = 1}
Combined Config:
Config {loggingLevel = 5, timeout = 20, retries = 3}
```

---

### 🔍 Explanation

* `max` is used for `loggingLevel` and `retries` because higher values mean more verbosity or more retries.
* `min` is used for `timeout` because we want the shortest timeout (most restrictive).

