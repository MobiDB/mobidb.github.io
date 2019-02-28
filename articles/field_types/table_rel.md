# Table relations set up #

With MobiDB Database Designer, users can create complex databases with multiple table relations. This article will show how to create table relations and access fields from the related tables.

<u>**Task:**</u>

Let’s assume we have two tables: ***Clients*** and ***Invoices***. When you generate invoices for your customers you want to select from the list of your customers and automatically fill in the following fields: ***billing address, contact name, email, phone***.


<u>**How to:**</u>

Clients table contains the following fields: ***Company, Email, Contact, Phone, Billing address, Shipping address***.

<img src="../../images/table_relations/1.png"  style="width:500px"/>  

***Figure1. Table view (phone)***

<img src="../../images/table_relations/2.png"  style="width:250px"/>  

***Figure 2. Table fields in the designer (phone)***

We strongly recommend changing field names used in formulas to make them unique and descriptive, so that you are able to easily identify the field when writing expressions.

<img src="../../images/table_relations/3.png"  style="width:250px"/>  

***Figure 3. Changing field name to be used in formulas***

We added a new table – ***Invoices***. And we need to get access to the customers’ data from the ***Clients*** table. In the designer, we add a ***Table reference*** control to the form. On the phone, tap <img src="../../images/table_relations/plus.png"  style="width:25x"/>    to proceed to the toolbox containing all available fields:

<img src="../../images/table_relations/4.png"  style="width:250px"/>  

***Figure 4. Adding fields from the toolbox (phone)***

Tap settings icon <img src="../../images/table_relations/edit.png"  style="width:25px"/>    to get access to the field options. Set field name, caption, select a table you want to link to, then select a field from that table you want to link to. Tap ***Save***.

We have just created table relation, so you will be able to select values from the related table in the dropdown list.

<img src="../../images/table_relations/5.png"  style="width:250px"/>

***Figure 5. Setting table relations***

Now we need to get access to other fields from the ***Clients*** table and fill in the values automatically upon selection of the company name. To do that, go back to the designer, tap the **Add** button <img src="../../images/table_relations/plus.png"  style="width:25px"/>   (on the phone) or just scroll the toolbox panel on your tablet to view all fields available from the related table – ***Related fields***.

<img src="../../images/table_relations/6.png"  style="width:250px"/>  

***Figure 6. Fields available from the related table (phone)***

Just tap the necessary field (or drag and drop it on the tablet). As a result, you will add the ***Calculable*** field with the pre-set expression that will get data from the related table field.

<img src="../../images/table_relations/7.png"  style="width:250px"/>

***Figure 7. Options of the related field***

In same way add all required fields: ***Billing address, Contact name, Phone, Email***. Tap ***Ok*** button to save changes and see the result.

Empty fields when no company is selected:

<img src="../../images/table_relations/8.png"  style="width:250px"/>  

***Figure 8. Empty fields when no company is selected***

The card is filled in automatically when the company name is selected:

<img src="../../images/table_relations/9.png"  style="width:250px"/>  

***Figure 9. Automatically filled in fields upon selection of the company name***

It’s also possible to proceed to the parent table by tapping the <img src="../../images/table_relations/eye.png"  style="width:25px"/>   icon and edit the necessary information. When you get back to the ***Invoices*** records, they will be updated to display the most recent data.

You can link to any field types including ***Pictures***.

So, you see how it is easy to create relations between the tables. Just add the ***Table reference*** field and in a couple of taps you get access to the required data. Users don’t need to have any programming experience and write any expressions at all. Everything is done in an intuitive and user-friendly manner.
