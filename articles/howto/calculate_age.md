# How to calculate age in MobiDB database

Based on the following [link](https://stackoverflow.com/a/1404/1099716) you need to add [calculable expression](../field_types/calc_exp.md) in the designer:

<img src="../../images/how_to/age/open_expressions.png"  style="width:800px"/>

Add the following expression called `diff`:

`getyear(getnow())-getyear(birthday)`

<img src="../../images/how_to/age/expression.png"  style="width:800px"/>

And add the following expression to the calculable field:

`if (birthday>AddYears(getdate(getnow()),-diff),diff-1,diff)`

<img src="../../images/how_to/age/calculable.png"  style="width:800px"/>

<img src="../../images/how_to/age/calculable_expression.png"  style="width:800px"/>

Result:

<img src="../../images/how_to/age/result.png"  style="width:800px"/>



Example can be found [here](../../examples/age.pdmd).
