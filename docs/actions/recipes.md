#recipes

Tweaks involving crafting table recipes.

## remove

<pre>tweak.recipes.remove(<a href="/arguments/string/">string</a> name)</pre>
<pre>tweak.recipes.remove(<a href="/arguments/stringlist/">stringlist</a> names)</pre>

Disable the specific recipe that matches the provided name

!!! note
	The [recipes command](/commands/recipes/) can be used to get a list of recipes for an item.

!!! example
	```python
	#remove the default crafting recipe for a torch
	tweak.recipes.remove("minecraft:torch");
	```
<br>

<pre>tweak.recipes.remove(<a href="/arguments/stack/">stack</a> output)</pre>
<pre>tweak.recipes.remove(<a href="/arguments/stacklist/">stacklist</a> outputs)</pre>

Disable all crafting recipes that match the provided output

!!! example
	```python
	#remove all crafting recipes for torches
	tweak.recipes.remove(<minecraft:torch>);
	```
<br>

---
## shaped

<pre>tweak.recipes.shaped(<a href="/arguments/string/">string</a> name, <a href="/arguments/stack/">stack</a> output, <a href="/arguments/recipeshaped/">recipeShaped</a> recipe)</pre>

Adds a new shaped crafting recipe

!!! example
	```python
	#adds a shaped recipe that turns 1 stone into diamond
	tweak.recipes.shaped("cheat_diamond", <minecraft:diamond>, [[<minecraft:stone>]]);
	```
<br>

---
## shapeless

<pre>tweak.recipes.shapeless(<a href="/arguments/string/">string</a> name, <a href="/arguments/stack/">stack</a> output, <a href="/arguments/recipeshapeless/">recipeShapeless</a> recipe)</pre>

Adds a new shapeless crafting recipe

!!! example
	```python
	#adds a shaped recipe that turns 1 stone into diamond
	tweak.recipes.shapeless("cheat_diamond", <minecraft:diamond>, [<minecraft:stone>]);
	```