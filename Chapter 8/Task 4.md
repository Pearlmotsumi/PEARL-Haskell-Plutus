HC8T4

* Defines the `Employee` type using **record syntax**
* Creates an employee named `richard` with 7.5 years of experience
* Includes a `main` function that prints the employee's information

```haskell
-- Define the Employee type using record syntax
data Employee = Employee
  { name :: String
  , experienceInYears :: Float
  } deriving Show

-- Create an employee named richard
richard :: Employee
richard = Employee
  { name = "Richard"
  , experienceInYears = 7.5
  }

-- Main function to run the code
main :: IO ()
main = do
  putStrLn "Employee Record:"
  print richard
```

### Sample output when run:

```
Employee Record:
Employee {name = "Richard", experienceInYears = 7.5}
```


