# Creating a Currency Exchange Emulator
To better understand magic methods and how they are used, we will be creating a Currency Exchange Emulator.

We will be following [this Replit](https://replit.com/@SD-Team/Python-1044#main.py) for this part of class.

Make sure to install numpy dependency if you are not working on replit: <br />
[setting up the virtual environment guide](https://github.com/michaelangelesz/currency_exchange_emulator#setting-up-your-virtual-environment) <br />
[installing dependencies guide](https://github.com/michaelangelesz/currency_exchange_emulator#using-pip-to-install-needed-dependencies)

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
<hr />

## Setting up your virtual environment
To get started, open your terminal and navigate to your project folder. Once you're inside of your project folder, you are ready to instantiate a virtual environment. To do so, in your terminal, enter the following command:

Mac:
```
python3 -m venv <env_name>
```

Windows:
```
py -m venv <env_name>
```

Now that your virtual environment has been built, you'll need to activate it. Do so by entering into your terminal:

Mac:
```
source <env_name>/bin/activate
```

Windows:
```
.\<env_name>\Scripts\activate
```

Upon doing so, you should see a change in your terminal, it may indicate that you are now inside of a virtual environment! Now, any dependencies we install will install to our virtual environment instead of our computer's global python shell.

Before moving on, we should add a gitignore file and make sure to reference our venv file inside of it.

• Create a .gitignore file (The content inside should simply be the <env_name>) <br />
• Alternatively, create a .gitignore file inside your new virtual environment (<env_name>) folder. Make the content inside simply one asterisk ( * ) and your <env_name> will be ignored.

## Using PIP to install needed dependencies
Next up, we need to install the dependencies that will form the core functionality of our application:<br />
• "numpy" - NumPy is the fundamental package for array computing with Python.<br />
To install this dependency, run the following code in your terminal:

Mac:
```
pip3 install numpy
```

Windows:
```
pip install numpy
```

Once the packages have been installed, type ls into your terminal once again. What has changed? Nothing? That's right! When we work with external packages in Node.js, we automatically generate a package.json file that has a directory of all of our dependencies. At this stage, if we were to post our code on github, contributors would have no idea what dependencies they would need in order to get the code to work! That's a problem!

Luckily, Pip has a handy fix for that exact problem. Enter the following command in your terminal:

```
pip freeze > requirements.txt
```

The pip freeze command will post a directory of all of your external packages and the versions that they are on inside of a text file! Whenever you clone an external python project, you can easily install all of the dependencies from the included requirements.txt file by simply running:

```
pip install -r requirements.txt
```
<hr />
