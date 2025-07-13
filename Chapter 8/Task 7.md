HC8T7

* Defines a new data type `Animal` with two constructors: `Dog String` and `Cat String` (where the `String` represents the animal's name)
* Implements a function `describeAnimal :: Animal -> String` that describes the animal
* Creates instances of a `Dog` and a `Cat`
* Prints their descriptions in the `main` function

```haskell
-- Define the Animal data type
data Animal = Dog String | Cat String deriving Show

-- Function to describe the animal
describeAnimal :: Animal -> String
describeAnimal (Dog name) = "This is a dog named " ++ name ++ "."
describeAnimal (Cat name) = "This is a cat named " ++ name ++ "."

-- Create instances of Dog and Cat
dog1 :: Animal
dog1 = Dog "Buddy"

cat1 :: Animal
cat1 = Cat "Whiskers"

-- Main function to run the code
main :: IO ()
main = do
  putStrLn $ describeAnimal dog1
  putStrLn $ describeAnimal cat1
```

### Sample Output:

```
This is a dog named Buddy.
This is a cat named Whiskers.
```

