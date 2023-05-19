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

## 3. Addfruit

a) Create a function Addfruit that takes a string as an input and either adds the string to the set;if the set doesn’t contain the string yet, or
prints “Fruit already in the bag” to the console.

```ruby
fruitset = set()      #create an empty set
def addFruit (fruit):
    """ This function adds fruits to set """
    if fruit not in fruitset:
        fruitset.add(fruit.upper())   #to avoid different string (banana and BANANA) being added
    else:
        print("Fruit already in the bag")

addFruit("Apple")
addFruit("Banana")
addFruit("APPLE")
```
===> Fruit already in the bag

```ruby
for fruit in fruitset:
    print(fruit)
```
===> BANANA
     APPLE

b) Adding several fruits at a time.  

Function addFruit2 take two fruits as parameters and adds them both to the set. 

```ruby
def addFruit2 (fruit1, fruit2):
    if fruit1 not in fruitset:
        fruitset.add(fruit1.upper())   
    else:
        print("Fruit1 already in the bag")
    if fruit2 not in fruitset:
        fruitset.add(fruit2.upper())   
    else:
        print("Fruit2 already in the bag")
    
addFruit2("Apple", "Banana")
print(fruitset)
```
===> {'BANANA', 'APPLE'}

Function addFruit3 takes any number of fruits and add the to the set. Add if it's not in the fuitset, else print "item already in the bag".

```ruby
def addFruit3(*fruit):    #we might pass 1 or whatever number of fruit 
    for item in fruit:
        if item not in fruitset:
            fruitset.add(item.upper())
        else:
            print("item already in the bag")

addFruit3("banana", "apple", "pineapple")
addFruit3("BANANA")
```
===> item already in the bag

## 4. Recursive Function
Write a recursive function that takes as input two integers “p” and “q” and returns p to the power of q.

```ruby
def power (p, q):
    if q == 0:     #recursive base case to avoid p power of negative -> infinitive
        return 1
    else:
        return p *  power(p, q-1)

#ANOTHER EXAMPLE - FACTORIAL RECURSIVE

def factorial (n):
    if n == 0:           #1 base case
     else:               #recursive case
         return n * factorial(n-1)
```
## 5. Fibonacci using iterative vs recursive functions
Write an function that takes an integer “n” as an input and returns the value of the n-th Fibonacci number
Remind: Fibonacci sequence: 0,1,1,2,3,5,8,13,21,...
- Using iterative function

```ruby
def fibonacci_iterative(n):
   i = 0    
   j = 1
   while (n > 1):
       t = j    
       j = j + i
       i = t    
       n = n - 1  #decrement n by 1 to prevent the loop going to infinity
   return i 
print(fibonacci_iterative(5))
```
===> 3
- Using recursive function

```ruby
def fibonacci_recursive(n):
    if n == 1:    #we need AT LEAST 2 base case to avoid going to infinity               
        return 0
    elif n == 2:                    
        return 1
    else:
        return fibonacci_recursive(n-1) + fibonacci_recursive(n-2)
print(fibonacci_recursive(5))
```
===> 3

## 6. Higher order function
Functions can also be considered as an object in Pytho; therefore, references to functions can be passed to other functions. Higher order function takes a function as a parameter and/or return a function. Let's take an example.

Use the filter()-function to create a list that only contains the numbers in “list1” that are divisible by 2
```ruby
list1 = [1,2,3,4,5,6,7,8,9]

def divisible_by_two(n):
    if n % 2 == 0:
        return True
    else:
        return False
list2 = list(filter(divisible_by_two, list1)) #filter(function-return T/F, data) is a built in function that we can avoid to use loop
print(list2)
```
===> [2, 4, 6, 8]

Differentiate with map()-function which modifies the list without filtering entries

```ruby
def divisible_by_two(n):
    return n/2     
list1 = map(divisible_by_two, list1)
for i in list1:
    print (i)
```
===> 0.5, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0, 4.5



