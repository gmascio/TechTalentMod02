Data Science Fundamentals: Python |
[Table of Contents](../index.ipynb)
- - - 
<!--NAVIGATION-->
Module 2. Python Data | [Simple Types](./01_simple_types.ipynb) | [Data Structures](./02_data_structures.ipynb): [Lists](./02_data_structures_lists.ipynb), [Tuples](./02_data_structures_tuples_part_1), [Sets](./02_data_structures_sets.ipynb), [Dictionaries](./02_data_structures_dictionaries.ipynb) | **[Exercises](./03_data_exercises.ipynb)**

# Data Structure Exercises

### Exercise 1:

In mathematics, the quadratic equation ax^2+bx+c=0 can be solved with the formula x=(−b±(√(b^2−4ac))/2a.

Write a function solve_quadratic, that returns both solutions of a generic quadratic as a pair (2-tuple) when the coefficients are given as parameters. It should work like this:

print(solve_quadratic(1,-3,2))

(2.0,1.0)

print(solve_quadratic(1,2,1))

(-1.0,-1.0)

You may want to use the math.sqrt function from the math module in your solution. Test that your function works in the main function!


```python
b=1
a=2
c=3

root = (((b ** 2) - 4)*(a)*(c))**(.5)
print(root)
```

    (2.5978681687064796e-16+4.242640687119285j)
    


```python
#getting our imports for math.sqrt
from math import sqrt

#create solve_quadratic func
def solve_quadratic(a, b, c):
    "Your Documentation String Here"
    #your code here
    root = ((b ** 2) - 4*(a)*(c))**(.5)
    quadratic1 = (-b + root)/(2*a)
    quadratic2 = (-b - root)/(2*a)
    print(quadratic1 , quadratic2)
    

#test case 1 should return (2.0,1.0)
print(solve_quadratic(1,-3,2))

#test case 2 should return (-1.0/-1.0)
print(solve_quadratic(1,2,1))
```

    2.0 1.0
    None
    -1.0 -1.0
    None
    

### Exercise 2:
Get a space-separated list of integers from the user, create a tuple of those integers. Then compute and print the result of hash(tuple).  [Hint](https://docs.python.org/3/library/functions.html#hash). **Hash()**

A **[hash](https://docs.python.org/3/library/functions.html#hash)** is an fixed sized integer that identifies a particular value. Each value needs to have its own hash, so for the same value you will get the same hash even if it's not the same object.


```python
#Get a space-separated list of integers from the user & create a tuple of those integers
integers = input("Input space seperated numbers")
type(integers)
list_integers = integers.split(' ')
print(list_integers)

numbers =[]
for n in list_integers:
    integer = n
    numbers.append(int(integer))
tuples = tuple(numbers)
    
print(numbers)
#print(hash())




#Then compute and print the result of hash(tuple)

```

    Input space seperated numbers6 6 8
    ['6', '6', '8']
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-55-3e70ab179be3> in <module>
          4 list_integers = integers.split(' ')
          5 print(list_integers)
    ----> 6 num = int(list_integers)
          7 print(num)
          8 numbers =[]
    

    TypeError: int() argument must be a string, a bytes-like object or a number, not 'list'


### Exercise 3:
Take the following two lists. Create a third list by picking a odd-index elements from the first list and even-index elements from the second.


```python
list1 = [3, 6, 9, 12, 15, 18, 21]
list2 = [4, 8, 12, 16, 20, 24, 28]
list3 = []
for index in range(1, len(list1),2):
    list3.append(list1[index])
    
for index2 in range(0,len(list2),2):
    list3.append(list2[index2])
        
        
print(list3)
    
```

    [6, 12, 18, 4, 12, 20, 28]
    


```python

```

### Exercise 4:
Take the following list. Slice it into three equal chunks and reverse each list.


```python
sampleList = [11, 45, 8, 23, 14, 12, 78, 45, 89]
```


```python
newlist = []
for i in range(0,len(sampleList),3):
    chunck = sampleList[i:i+3]
    chunck.reverse()
    newlist.append(sampleList[i:i+3])
                   
print(newlist)
```

    [[11, 45, 8], [23, 14, 12], [78, 45, 89]]
    

### Exercise 5: 
Iterate through a given list (`rollNumber`) and check if a given element already exists in the given dictionary (`sampleDict`) as a key’s value. If not, delete it from the list.


```python
rollNumber = [47, 64, 69, 37, 76, 83, 95, 97]
sampleDict ={'Zach':47, 'Emma':69, 'Kelly':76, 'Jason':97}
```

Please know this is a hard problem, and is advanced for a data structures  exercise. It is designed to be the challenge problem, because this exercise incorporates knowledge from material we have yet to go through. The key is to keep in mind the nature of dictionaries, and how our control flow/iteration is performed in these `for` loops. 

There are two ways to approach this problem, our approach is to delete elements from `rollNumber`, the alternate is to add the matches from `rollNumber` and `sampleDict`'s values to a new list. The second approach is easier, but you should do the first approach for this exercise. Here is one example of the first approach, but notice how 95 is included here, and ponder why.


```python
#Incorrect, will include #95
#iterate through the elements in rollNumber
for n in rollNumber:
    #check if a given element already exists in sampleDict as the key, n's value pair.
    if n not in sampleDict.values():
        #if an element already exists in the given dict then we remove it
        rollNumber.remove(n) 
    #if n is in sampleDict.values, continue
    else:
        continue

print(rollNumber)
```

    [47, 69, 76, 95, 97]
    


```python
#your code here, correct answer is [47, 69, 76, 97]
result = []
for n in rollNumber:
    if n in sampleDict.values():
        result.append(n) 
    else:
        continue

print(result)

```

    [47, 69, 76, 97]
    

## Extra Points
- - -

1. ***Optional Exercise (Extra Points)***.  Write a Python program to convert a tuple to a string.


```python

```

2. ***Optional Exercise (Extra Points)***.  Write a Python program to check whether an element exists within a tuple.


```python

```

3. ***Optional Exercise (Extra Points)***.  Write a Python program to print a tuple with string formatting.


```python

```

- - - 
<!--NAVIGATION-->
Module 2. Python Data | [Simple Types](./01_simple_types.ipynb) | [Data Structures](./02_data_structures.ipynb) | **[Exercises](./03_data_exercises.ipynb)**
<br>
[Top](#)

- - -

Copyright © 2020 Qualex Consulting Services Incorporated.
