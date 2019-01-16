#anvil

Tweaks involving changing of anvil recipes and behaviour.

<br>

---
## add

<pre>tweak.anvil.add(<a href="/arguments/stack/">stack</a> left, <a href="/arguments/stack/">stack</a> right, <a href="/arguments/stack/">stack</a> output, <a href="/arguments/integer/">integer</a> cost)</pre>

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

<pre>tweak.anvil.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.anvil.remove(<a href="/arguments/stack/">stack</a> item)</pre>

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

<pre>tweak.anvil.disable(<a href="/arguments/string/">string</a> value)</pre>

A helper action that disables a specific group of anvil recipes, the current values are :

### books
<pre>tweak.anvil.disable("books")</pre>

Disables any recipes where an item is enchanted using a book, e.g `Diamond Sword + Enchanted Book`

### repairs
<pre>tweak.anvil.disable("repairs")</pre>

Disables any recipes where an item is repaired, e.g `Diamond Sword + Diamond`

### combinebooks
<pre>tweak.anvil.disable("combineBooks")</pre>

Disables any recipes where two books are combined, e.g `Enchanted Book + Enchanted Book`

### combinerepairs
<pre>tweak.anvil.disable("combineRepairs")</pre>

Disables any recipes where two items are combined, e.g `Diamond Sword + Diamond Sword`

<br>

---
## setBreakChance

<pre>tweak.anvil.remove(<a href="/arguments/float/">float</a> chance)</pre>

Sets the chance for the anvil to take break damage on use, default vanilla chance is 0.15.

!!! example
	```python
	#sets the anvil to break 75% of the time
	tweak.anvil.setBreakChance(0.75);
	```