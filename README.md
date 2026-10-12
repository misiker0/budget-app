# Budget App

A simple Python budget tracker. Create spending categories, record deposits, withdrawals, and transfers, and generate a text bar chart showing how spending is split across categories.

Built as part of the freeCodeCamp Scientific Computing with Python certification.

## Features

- `Category` class with a ledger of transactions
- `deposit`, `withdraw`, `transfer`, `get_balance`, and `check_funds` methods
- Withdrawals and transfers are blocked when funds are insufficient
- Printing a category shows a formatted statement
- `create_spend_chart` draws a bar chart of the percentage spent per category, rounded down to the nearest 10

## Usage

```python
food = Category('Food')
food.deposit(1000, 'initial deposit')
food.withdraw(10.15, 'groceries')
food.withdraw(15.89, 'restaurant and more food for dessert')
clothing = Category('Clothing')
food.transfer(50, clothing)
print(food)
```

Output:

```
*************Food*************
initial deposit        1000.00
groceries               -10.15
restaurant and more foo -15.89
Transfer to Clothing    -50.00
Total: 923.96
```

### Spend chart

```python
food = Category('Food')
clothing = Category('Clothing')
auto = Category('Auto')
food.deposit(1000)
clothing.deposit(1000)
auto.deposit(1000)
food.withdraw(60)
clothing.withdraw(20)
auto.withdraw(10)
print(create_spend_chart([food, clothing, auto]))
```

Output:

```
Percentage spent by category
100|          
 90|          
 80|          
 70|          
 60| o        
 50| o        
 40| o        
 30| o        
 20| o  o     
 10| o  o  o  
  0| o  o  o  
    ----------
     F  C  A  
     o  l  u  
     o  o  t  
     d  t  o  
        h     
        i     
        n     
        g     
```

## Running it

Requires Python 3.

```
python budget.py
```

Add your own test code at the bottom of the file, or import the classes from another script.

## What I practiced

- Object-oriented design: classes, instance attributes, and methods
- String formatting with f-strings (alignment, padding, decimals)
- Nested loops to build a text chart
- Debugging scope, return values, and off-by-one errors
