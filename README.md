# Live Version 
https://front-end-expense-tracker.netlify.app/

# Image of application
![alt text](https://github.com/jedhabush/Expense_Tracker_React/blob/main/expenseTracker.png)
----------------------------------------------------------------------------------------------
![alt text](https://github.com/jedhabush/Expense_Tracker_React/blob/main/expenseTracker2.png)
----------------------------------------------------------------------------------------------
# Expense_Tracker_React
A simple react project to track personal expenses. The focus was to create a Front-End app that utilizes the fundamentals of react using the proper way to split files and use the power of ```useState hook```. I believe the best way to maintain a skill is to keep using it. 


# Features
- User can see expenses by year
- When user filter by year,  user interface (UI) automatically updates
- User can add new expense
- User can see which month had the most expenses 

# Challenges 
- Figuring out the best way to update the state depending on the previous state or snapshot. To give a bit of prespective to what I'm trying to do, I wanted to gather all the values for all form inputs when user add a **new expense** and then combine them into an object when the form is submitted. One way of storing these values
and makeing sure that they survive, even if that function would be re-executed is to use ```useState```.

In the conext of this porject I wanted to update current expenses list when the user submits a **new expense** . To do that I need to add the **new expense** to the existent expenses array (Dummy data) then render it. The million dollars question is how to update a list of expenses depending on a previous list of expenses? The solution is to pass a function as an argument to the state updating function as follow:

``` javascript
const [expenses, setExpenses] = useState(DummyExpenses);
  const addExpenseHandler = (expense) => {
    //use setState as callback function if you rely on prev data/states to ensure getting the latest data
    setExpenses((prevExpenses) => [expense, ...prevExpenses]);
```

implementing ```useState``` that way, will automatically receive the latest state snapshot and that helps me to get the previous expenses automatically by React. As a result,  I would be able to return the new array with the new expense.


# Future upgrades

- Implement a back-end to save the added expenses in a database. Currently, when you add a new expense to the list, it would disappear when the page is reloaded.
- It would be awesome if I figured a way to connect my personal bank to track expenses and make the whole process autonomous 
