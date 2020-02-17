
# If statements

The `if` statements play a fundamental role controlling the logical flow of the code. A sequence of decision rules instruct the computer to execut specific commands. If statements evaluate whether a condition is `True` or `False` and at that point the code bifurcates. Sometimes there multiple conditions as part of a single `If` statements, in which the code could branch into many different options.

## Odd or even?

A simple exercise to learn the basic structure of `If` staments is to compute and print whether a given number is odd or even. Even numbers are divisible by 2 with a reminder of zero whereas odd numbers are not divisible by 2 and have remainder greater than zero. To perform this operation we can use the Python `modulo` operator, which represented by `%`.


```python
# If and Else statement
value = 8

if value % 2 == 0:
    print('Number is even')
else:
    print('Number is odd')

```

    Number is even


Using the same code within a `for loop` we can easily check all the numbers from one to ten.


```python
for value in range(1,11):
    if value % 2 == 0:
        print('Number',value,'is even')
    else:
        print('Number',value,'is odd')
        
```

    Number 1 is odd
    Number 2 is even
    Number 3 is odd
    Number 4 is even
    Number 5 is odd
    Number 6 is even
    Number 7 is odd
    Number 8 is even
    Number 9 is odd
    Number 10 is even


## Aridity Index

`If statements` allow us to include multiple options using the `elif` (else if) keyword accompained by a conditional statement. Let's look at an example involving the classification of different environments based on the Aridity Index (AI) proposed by the United Nations Environmental Program (UNEP).

The Aridity Index (AI) has gone through many versions and is currently defined by the Food and Agriculture Organization (FAO) as the ratio of the total annual precipitation (P) and the total annual cummulative potential evapotranspiration (PET):

$$ AI = \frac{P}{PET}  $$



Table of climate classification according to the aridity index defined by the FAO
```
| Climate class |       Value      |
|---------------|------------------|
| Desert        |        AI ≤ 0.03 |
| Hyper-arid    | 0.03 < AI ≤ 0.05 |
| Arid          | 0.05 < AI ≤ 0.20 |
| Semi-arid     | 0.20 < AI ≤ 0.50 |
| Dry           | 0.50 < AI ≤ 0.65 |
| Sub-humid     | 0.65 < AI ≤ 0.75 |
| Humid         |        AI > 0.75 |
```

## References

Spinoni, J., Vogt, J., Naumann, G., Carrao, H. and Barbosa, P., 2015. Towards identifying areas at climatological risk of desertification using the Köppen–Geiger classification and FAO aridity index. International Journal of Climatology, 35(9), pp.2210-2222.


```python
# Example
P = 1000   # mm per year
PET = 1800 # mm per year
AI = P/PET

if AI <= 0.03:
    climate_classification = 'Desert'
    
elif AI > 0.03 and AI <= 0.05:
    climate_classification = 'Hyper-arid'
    
elif AI > 0.05 and AI <= 0.2:
    climate_classification = 'Arid'

elif AI > 0.2 and AI <= 0.5:
    climate_classification = 'Semi-arid'

elif AI > 0.5 and AI <= 0.65:
    climate_classification = 'Dry'
    
elif AI > 0.65 and AI <= 0.75:
    climate_classification = 'Sub-humid'
    
else:
    climate_classification = 'Humid'
    
print('Climate classification is:',climate_classification,'(AI='+str(round(AI,2))+')')
```

    Climate classification is: Dry (AI=0.56)


## Find leap years

Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400. For example, the years 1700, 1800, and 1900 are not leap years, but the years 1600 and 2000 are (United States Naval Observatory).


```python
# Leap years
year = 2000

if year%4 == 0:
    if year%100 > 0:
        print(year,'is a leap year.')
    else:
        if year%400 == 0:
            print(year,'is a leap year.')
        else:
            print(year,'is not a leap year.')
else:
    print(year,'is not a leap year.')

```

    2000 is a leap year.

