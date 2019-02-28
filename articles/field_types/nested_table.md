# Nested table (one to many relation, master-detail) #

Nested table allows to set up one to many relationship like in sample provided below:

<img src="../../images/nested_table/nested_table_sample.png" style="width:800px"/>

Let's create order details sample to see how it can be set up.
Create blank database:

<img src="../../images/nested_table/blank_db.png" style="width:800px"/>

Before we start adding nested table let's add "product" table with the following structure:

<img src="../../images/nested_table/product.png" style="width:800px"/>

Then create "orders" table and open designer:

<img src="../../images/nested_table/empty_table.png" style="width:800px"/>

Let's add order date field:

<img src="../../images/nested_table/date.png" style="width:800px"/>

Now we are ready to add nested table control:

<img src="../../images/nested_table/nested_table_control.png" style="width:800px"/>

In order to design nested table we need to open designer for it:

<img src="../../images/nested_table/design_nested_table.png" style="width:800px"/>

Now let's add table relation to "Product" table. It is not related to our article, for more info take a look at [Table relation set up article](./table_rel.md)

<img src="../../images/nested_table/table_reference.png" style="width:800px"/>

In order to calculate total we need to take product price and to multiply it by Quantity. Start from adding calculable field:

<img src="../../images/nested_table/calculable.png" style="width:800px"/>

Configure "total" calculable formula:
<img src="../../images/nested_table/total.png" style="width:800px"/>

In order to get back to parent table design use bread crumbs:

<img src="../../images/nested_table/bread_crumbs.png" style="width:800px"/>

Let's configure total column in parent table:

<img src="../../images/nested_table/global_total.png" style="width:800px"/>

For more info regarding total expression take a look at [Calculable expressions article](./use_exp.md)

Now our nested table is up and running:

<img src="../../images/nested_table/nested_table_ready.png" style="width:800px"/>
