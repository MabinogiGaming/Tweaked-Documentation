#loot

Tweaks involving changing of anvil recipes and behaviour.

<br>

---
## add

**tweak.anvil.add([stack](/arguments/stack/) left, [stack](/arguments/stack/) right, [stack](/arguments/stack/) output, [integer](/arguments/integer/) cost)**  

Adds a recipe to the anvil, where the left + right items combine to give the output.
The cost is the amount of experience levels required.

!!! example
	```python
	#combine an apple, carrot and 30 experience levels to craft a diamond
	tweak.anvil.add(<minecraft:apple>, <minecraft:carrot>, <minecraft:diamond>, 30);
	```

<br>

---
## remove

**tweak.anvil.remove([all](/arguments/all/) all)**  
**tweak.anvil.remove([stack](/arguments/stack/) item)**  

Remove all or any recipe with the specified input, essentially blacklisting that input.
The input can be either the left or the right slot item.

!!! example
	```python
	#disable the repairing, enchanting or combining of diamond swords
	tweak.anvil.remove(<minecraft:sword_diamond>);
	```

<br>

---
## disable

**tweak.anvil.disable([string](/arguments/string/) value)**   

A helper action that disables a specific group of anvil recipes, the current values are :

### books
**tweak.anvil.disable("books")**   

Disables any recipes where an item is enchanted using a book, e.g `Diamond Sword + Enchanted Book`

### repairs
**tweak.anvil.disable("repairs")**   

Disables any recipes where an item is repaired, e.g `Diamond Sword + Diamond`

### combinebooks
**tweak.anvil.disable("combineBooks")**   

Disables any recipes where two books are combined, e.g `Enchanted Book + Enchanted Book`

### combinerepairs
**tweak.anvil.disable("combineRepairs")**   

Disables any recipes where two items are combined, e.g `Diamond Sword + Diamond Sword`

<br>

---
## setBreakChance

**tweak.anvil.remove([float](/arguments/float/) chance)**

Sets the chance for the anvil to take break damage on use, default vanilla chance is 0.15.

!!! example
	```python
	#sets the anvil to break 75% of the time
	tweak.anvil.setBreakChance(0.75);
	```