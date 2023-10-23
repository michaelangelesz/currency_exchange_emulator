# Creating a Currency Exchange Emulator
To better understand magic methods and how they are used, we will be creating a Currency Exchange Emulator.

We will be following [this Replit](https://replit.com/@SD-Team/Python-1044#main.py) for this part of class.

## Getting Started
First, let's explore the code we already have. We have provided you with a base Currency class that contains a class dictionary called currencies , which contains some currency exchange rates, using USD as a base value. Feel free to update this table if you desire. Note that doing so will change the expected output of the program.

We have also provided you with the class constructor and a changeTo() function for converting between currencies. Feel free to play with these elements.

## Building Magic Methods
Your task for this activity is to complete the necessary magic methods to allow the provided code to function. The first three have been outlined in the Replit for you, the others you will need to add manually from scratch. For the pre-defined functions, make sure to remove the 'pass' statement before coding the desired return values, or they may not work. These methods are:

`__repr__(self)` - This method returns the string to be printed. This should be the value rounded to two digits, accompanied by its acronym.<br />
`__str__(self)` - This method returns the same value as __repr__(self) .<br />
`__str__(self)` - This method returns the same value as __repr__(self) .<br />
`__add__(self,other)` - Defines the '+' operator. If other is a Currency object, the currency values are added, and the result will be the unit of self. If other is an int or a float, it will be treated as a USD value.<br />
`__iadd__(self,other)` - This is the same as (calls) __add__(self,other) .<br />
`__radd__(self,other)` - This method is similar to __add__(self,other), but occurs when an int or float tries to add a Currency object. (Treat the int/float as having a USD value.)<br />
`__sub__(self,other)` - All __sub__(self,other) type functions are parallel to __add__(self,other) type functions.<br />
`__isub__(self,other)`<br />
`__rsub__(self,other)`<br />

## Testing Your Currency Class
After you have defined your magic methods, test your Currency class by running the given code (the code included with the Replit). It should run with no errors if you have implemented all of the magic methods correctly.

In case you changed it, the test code is:

```
v1 = Currency(23.43, "EUR")
v2 = Currency(19.97, "USD")
print(v1 + v2)
print(v2 + v1)
print(v1 + 3) # an int or a float is considered to be a USD value
print(3 + v1)
print(v1 - 3) # an int or a float is considered to be a USD value
print(30 - v2) 
```

Your output should be:

```
40.65 EUR
47.14 USD
26.02 EUR
30.17 USD
20.84 EUR
10.03 USD
```

Remember, if you changed the values of the currency exchange rates, this output will also be different.

If you need extra help, the solution code can be found [here](https://replit.com/@SD-Team/1044-Solution#main.py).
