# recipeShapeless

A special argument type that allows creation of a shapeless crafting recipe.

A shapeless recipe is one that can have the inputs placed in any order, their positioning doesn't matter.

## Argument

The arrangement of a recipe is important not important, inputs can be placed in any order :  
<pre>[&lt;A&gt;,&lt;B&gt;,&lt;C&gt;,&lt;D&gt;,&lt;E&gt;,&lt;F&gt;,&lt;G&gt;,&lt;H&gt;,&lt;I&gt;]</pre>

Where A-I are [ingredients](/arguments/ingredient/)

The number of ingredients can be anything from 1-9.

The best way to illustrate this is examples of vanilla recipes :

!!! example
	```python
	#flint and steel (1 flint, 1 iron)
	[<minecraft:flint>, <ingotIron>]
	```
