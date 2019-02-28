# Accumulated balance set up #

Accumulated balance is an exceptionally useful feature for users who would like to define and run balances for the specified fields. The balance calculations are automatically updated, thus no user intervention is required to get the actual state of the values.

This tutorial displays how to create an accumulated balance sheet from scratch.

To begin with, let us create the database that we can run for our little imaginary electronics shop.
The basic database tables list for such undertaking implies the availability of the following tables:
***Customers*** and ***Employees*** – the tables that keep records of our customers and employees, as well as ***Products*** table that lists the electronic items we sell. These auxiliary tables do not take part in our calculations.

<img src="../../images/acc_balance/1.png"  style="width:500px"/>

<img src="../../images/acc_balance/2.png"  style="width:500px"/>

The rest two tables named ***In*** and ***Out*** are the main tables that we use to debit incoming goods and to issue invoices to our customers.

The ***In*** table keeps the daily records of the electronics supplied to our storage.

<img src="../../images/acc_balance/3.png"  style="width:500px"/>

Whereas the ***Out*** table maintains the list of the invoices issued to our customers by the employees.

<img src="../../images/acc_balance/4.png"  style="width:500px"/>


In such scenario, the supply of electronic devices to our shop and their subsequent selling are the two processes that run separately.  This means we can have difficulties with the calculation of products in stock and cannot easily define the list of currently available devices. This is the case when the accumulated balance feature comes in handy.

The next steps will describe the process of adding the accumulated balance feature to our database in order to keep track of the items available in stock.

1.Add a new accumulated balance by tapping on the ***Plus*** icon in the upper right corner of the instrument panel.

<img src="../../images/acc_balance/5.png"  style="width:350px"/>

2.Specify the accumulated balance name and tap ***OK*** to confirm.

<img src="../../images/acc_balance/6.png"  style="width:350px"/>


3.To configure the accumulated balance, tap on the ***Open configurator*** option.

<img src="../../images/acc_balance/7.png"  style="width:350px"/>

4.Then, tap ***Open structure editor*** to run it.

<img src="../../images/acc_balance/8.png"  style="width:350px"/>

5.The accumulated balance structure consists of two field types. The ***detail*** fields that specify the fields we would like to run the balance for and the ***aggregation*** fields that display the data itself.

<img src="../../images/acc_balance/9.png"  style="width:350px"/>

6.Set the detail field name to ***Product*** and specify the field type. In most cases, the ***Auto*** type will be the reasonable choice.

<img src="../../images/acc_balance/10.png"  style="width:350px"/>


In case you made a mistake or would like to modify/delete the existing detail field simply tap on the options menu icon to the right of the field and select either ***Edit*** or ***Delete***. The same is true for the aggregation fields.

<img src="../../images/acc_balance/11.png"  style="width:350px"/>

7.Set the aggregation field name to ***Availability*** and tap ***OK*** to confirm.

<img src="../../images/acc_balance/12.png"  style="width:350px"/>

This is how your accumulated balance structure should look like.

<img src="../../images/acc_balance/13.png"  style="width:350px"/>


After the balance structure is created, we have to configure the settings by running the ***Configurator***.

8.Tap on the ***Plus*** button to add the data source to our balance.

<img src="../../images/acc_balance/14.png"  style="width:350px"/>

9.As data source we should specify ***In.Items*** nested table that contains the actual number of devices supplied to our storage for the entire period.

<img src="../../images/acc_balance/15.png"  style="width:350px"/>

10.Now, set the ***Product*** field from the ***In.Items*** nested table as the detail field value.

<img src="../../images/acc_balance/16.png"  style="width:500px"/>

11.Then specify the ***Quantity*** field as the aggregation field value.

<img src="../../images/acc_balance/17.png"  style="width:500px"/>

The active green ***plus*** sign to the left of the data source signals that the data from this source will be added to our balance.

The next step is to add the ***Out*** table data to our balance that will be subtracted from the ***In*** table data.

12.Tap on the ***plus*** icon once again to add the ***Out*** table data source.

<img src="../../images/acc_balance/18.png"  style="width:500px"/>

13.Set the ***Out.Items list*** table that lists the devices invoiced by the employees as the data source for ***Out*** table. Then specify the ***Product*** and ***Quantity*** fields accordingly.

<img src="../../images/acc_balance/19.png"  style="width:350px"/>

The active red ***minus*** sign to the left of the ***Out.Items list*** data source signals that the data from this source will be subtracted from our balance.

Eventually, the configured balance should look like this.

<img src="../../images/acc_balance/20.png"  style="width:500px"/>


14.Tap on the check mark on the instrument panel to exit the configurator and save the accumulated balance.

<img src="../../images/acc_balance/21.png"  style="width:350px"/>

The figure below displays the newly created ***Stock*** balance that lists the devices from our storage and counts the number of devices left in stock. As seen, some of the devices are out of stock, which is proved by the ***0*** value in the ***Availability*** column. In some cases this information may look quite redundant and can be excluded by using the appropriate filter.

<img src="../../images/acc_balance/22.png"  style="width:500px"/>

15.To configure the filter tap on the ***Filter*** icon in the instrument panel.

<img src="../../images/acc_balance/23.png"  style="width:350px"/>

16.Set the filter parameters as specified below and tap **OK** to confirm the changes.

<img src="../../images/acc_balance/24.png"  style="width:350px"/>

As a result, our balance lists only those devices that are currently available in stock.

<img src="../../images/acc_balance/25.png"  style="width:500px"/>

The database used in this sample is available under the following link:
http://perpetuumsoft.com/Support/downloads/mobidb/Electronics_shop_sample.zip
