#brewing

Tweaks involving changing of brewing recipes created with the Brewing Stand.

<br>

---
## add

**tweak.brewing.add([stack](/arguments/stack/) ingredient, [stack](/arguments/stack/) input, [stack](/arguments/stack/) output)**  

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

**tweak.brewing.remove([all](/arguments/all/) all)**  
**tweak.brewing.remove([stack](/arguments/stack/) ingredient)**  

Remove all or a recipe with the specified ingredient.

!!! example
	```python
	#disable all recipes with sugar as the ingredient
	tweak.brewing.remove(<minecraft:sugar>);
	```

<br>