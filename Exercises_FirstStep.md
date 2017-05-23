1. Change the program so it reads two arguments from the command line, and prints out a message using both of them
```haskell
 module Main where
 import System.Environment
 
 main :: IO ()
 main = do
     args <- getArgs
     putStrLn ("Hello, " ++ (foldr (++) "" args))
```

2. Change the program so it performs a simple arithmetic operation on the two arguments and prints out the result. 
You can use `read` to convert a string to a number, and `show` to convert a number back into a string. 
Play around with different operations.  
*NOTE* `let` does not pair with `in` in `do` block
```haskell
 module Main where
 import System.Environment
 
 main :: IO ()
 main = do
     [a, b] <- getArgs
     putStrLn (a ++ " + " ++ b ++ " = " ++ (calc a b))
         where 
            calc sa sb = show $ (read sa :: Int) + (read sb :: Int)
```

3. `getLine` is an IO action that reads a line from the console and returns it as a string. 
Change the program so it prompts for a name, reads the name, and then prints that instead of the command line value
```haskell
 module Main where
 import System.Environment
 
 main :: IO ()
 main = do
     putStrLn "What's your name?"
     args <- getLine
     putStrLn $ "Hello, " ++ args
```
