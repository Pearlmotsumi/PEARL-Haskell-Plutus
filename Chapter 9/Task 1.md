HC9T1: Define a Parametric Type Synonym

* Defines a **parametric type synonym** `Entity a` to represent entities with addresses of any type `a`
* Creates example entities using different types for the address
* Prints them in `main`

```haskell
-- Parametric type synonym for an entity with an address of type a
type Entity a = (String, a)  -- (Name, Address)

-- Example entities
entity1 :: Entity String
entity1 = ("CompanyA", "123 Blockchain Ave")

entity2 :: Entity (Int, Int)
entity2 = ("WarehouseB", (45, 78))  -- Coordinates as address

-- Main function
main :: IO ()
main = do
  putStrLn "Entity 1:"
  print entity1

  putStrLn "\nEntity 2:"
  print entity2
```

### Sample output:

```
Entity 1:
("CompanyA","123 Blockchain Ave")

Entity 2:
("WarehouseB",(45,78))
```


