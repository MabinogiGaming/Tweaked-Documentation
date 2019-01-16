#brewing

Tweaks involving changing of brewing recipes created with the Brewing Stand.

<br>

---
## add

<pre>tweak.brewing.add(<a href="/arguments/stack/">stack</a> ingredient, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/stack/">stack</a> output)</pre>

Adds a brewing recipe where an ingredient can be brewed with an input to create an output.
Potions can be specified using nbt data, a list of potion types can be found [here](/glossary/potions/).

!!! example
	```python
	#adds a brewing recipe where a diamond can be brewed into a water bottle to create a strong leaping potion
	tweak.brewing.add(<minecraft:diamond>, <minecraft:potion:0:1:{Potion:"minecraft:water"}>, <minecraft:potion:0:1:{Potion:"minecraft:strong_leaping"}>);
	```

<br>

---
## remove

<pre>tweak.brewing.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.brewing.remove(<a href="/arguments/stack/">stack</a> ingredient)</pre>

Remove all or a recipe with the specified ingredient.

!!! example
	```python
	#disable all recipes with sugar as the ingredient
	tweak.brewing.remove(<minecraft:sugar>);
	```

<br>