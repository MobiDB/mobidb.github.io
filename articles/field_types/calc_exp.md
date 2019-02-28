# Invisible calculable variables #

Calculable expressions feature is introduced to minimize the number of calculable fields on the form required to perform specific calculations.

To get deeper in detail, let’s see into a simple sample.

Let’s assume we have a table that stores the customer first name and last name in separate fields and we have a task to output both first and last name as a single record in customers list within ‘Orders’ table. To achieve this we can use a Calculable Expression in ‘Customer’ table to merge both fields into one.

<img src="../../images/calc_exp/1.png"  style="width:500px"/>


Click/tap on the Calculable Expressions icon located in the upper toolbar to run the Calculable Expressions manager.

<img src="../../images/calc_exp/2.png"  style="width:500px"/>

Set the Expression name and specify the formula that merges customer first and last name into a single value.

<img src="../../images/calc_exp/3.png"  style="width:300px"/>


Exit the Expressions manager window by pressing ‘OK’ to confirm the changes.

Then, add the Table reference control to ‘Orders’ table and check to make sure the expression name **‘FLName’** is available as a column for 'Customers' table.

Select 'FLName' as the column value and exit the forms designer.

<img src="../../images/calc_exp/4.png"  style="width:300px"/>


Now open the customers dropdown list in ‘Orders’ table to see the customer first and last names displayed as a single value.

<img src="../../images/calc_exp/5.png"  style="width:500px"/>
