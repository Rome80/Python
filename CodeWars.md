# Beginner Series 

## Instructions - Exercise 1

Given two integers a and b, which can be positive or negative, find the sum of all the integers between and including them and return it. 
If the two numbers are equal return a or b.

## Solution

def get_sum(a,b):
    sum = 0
   
    if a > b:
        x=range(b,a+1)
    else:
        x=range(a,b+1)

    for i in x:
        sum += i
        
    return sum

## Instructions - Exercise 2

ATM machines allow 4 or 6 digit PIN codes and PIN codes cannot contain anything but exactly 4 digits or exactly 6 digits.

If the function is passed a valid PIN string, return true, else return false.

## Solution

def validate_pin(pin):
    if (len(str(pin)) == 4) or (len(str(pin)) == 6):
        if pin.isnumeric() != True:
            return False
        if int(pin) < 0:
            return False
        return True
    else:
        return False
        
## Instructions - Exercise 3

In a factory a printer prints labels for boxes. For one kind of boxes the printer has to use colors which, for the sake of simplicity, are named with letters from a to m.

The colors used by the printer are recorded in a control string. For example a "good" control string would be aaabbbbhaijjjm meaning that the printer used three times color a, four times color b, one time color h then one time color a...

Sometimes there are problems: lack of colors, technical malfunction and a "bad" control string is produced e.g. aaaxbbbbyyhwawiwjjjwwm with letters not from a to m.

You have to write a function printer_error which given a string will return the error rate of the printer as a string representing a rational whose numerator is the number of errors and the denominator the length of the control string. Don't reduce this fraction to a simpler expression.

The string has a length greater or equal to one and contains only letters from ato z.

## Solution

def printer_error(s):

    errors = 0
    for i in str(s):
        if i > 'm':
            errors += 1
    return (str(errors) + "/" + str(len(s)))
    
## Instructions - Exercise 4

Complete the method/function so that it converts dash/underscore delimited words into camel casing. 
The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).

## Examples

"the-stealth-warrior" gets converted to "theStealthWarrior"
"The_Stealth_Warrior" gets converted to "TheStealthWarrior"

## Solution

def to_camel_case(text):

    i = 1
    text = text.replace('_', '-')
    text = text.split('-')
    text =  text[0] + ''.join(i.capitalize() for i in text[1:])
    return text
    
## Instructions - Exercise 5

In a small town the population is p0 = 1000 at the beginning of a year. 
The population regularly increases by 2 percent per year and moreover 50 new inhabitants per year come to live in the town. 
How many years does the town need to see its population greater or equal to p = 1200 inhabitants?

## Examples

At the end of the first year there will be: 
1000 + 1000 * 0.02 + 50 => 1070 inhabitants

At the end of the 2nd year there will be: 
1070 + 1070 * 0.02 + 50 => 1141 inhabitants (** number of inhabitants is an integer **)

At the end of the 3rd year there will be:
1141 + 1141 * 0.02 + 50 => 1213

It will need 3 entire years.

## Solution

def nb_year(p0, percent, aug, p):
    years = 0
    
    while (p0 < p):
        years += 1
        p0 = p0 + int(p0*(percent/100)) + aug
    
    return years
   


    
    
    

