# Easy-Fun
## 1. Take recursive function that computes the factorial of a given number

```ruby
def factorial(n):   #define a function factorial take n is parameter
    if n==1:
        return 1
    else:
        return n*factorial(n-1)
print(factorial(10))   
```
===> 3628800

## 2. Some easy functions

a) A function that takes a string as an input and prints the UPPERCASED version of that string to the console.
-> without "return" statement

```ruby
mystring = "this is my first string"
print(mystring.upper())

def stringUpper(str):
    print(str.upper())
stringUpper("hello github")
```
===> THIS IS MY FIRST STRING

===> HELLO GITHUB

b)  A function that takes a string as an input and returns the UPPERCASED version of that string. Then print that string to the output. 
-> includes "return" statement

```ruby
def upper (mystring):
    return mystring.upper()
print(upper("this is my second string"))
```
===> THIS IS MY SECOND STRING

Both cases can give the same result!!! 

c) A function that takes a float as an input, rounds it down to the next integer and then returns the float an the corresponding integer as a tupel.

```ruby
def myfunc (float):
    x = int(float)   #round the float down to the next integer  
    return (float, x) #return the float and corresponding integer as a tupel
print(myfunc(3.9))
```
===> (3.9, 3)
