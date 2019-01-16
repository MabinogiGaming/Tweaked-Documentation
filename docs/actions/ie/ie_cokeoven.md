#ie.cokeoven

Tweaks involving the Coke Oven from Immersive Engineering.

<br>

---
## add

<pre>tweak.ie.cokeoven.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/integer/">integer</a> time, <a href="/arguments/integer/">integer</a> creosote)</pre>
<pre>tweak.ie.cokeoven.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/dict/">dict</a> input, <a href="/arguments/integer/">integer</a> time, <a href="/arguments/integer/">integer</a> creosote)</pre>

Adds a new recipe to the coke oven.

!!! example
	```python
	#adds recipe where stone turns into diamonds and 200mb of creosote, taking 1000 ticks
	tweak.ie.cokeoven.add(<minecraft:diamond>, <minecraft:stone>, 1000, 200);
	```
<br>

---
## remove

<pre>tweak.ie.cokeoven.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.ie.cokeoven.remove(<a href="/arguments/stack/">stack</a> output)</pre>
<pre>tweak.ie.cokeoven.remove(<a href="/arguments/stacklist/">stacklist</a> outputs)</pre>

Removes all recipes from the coke oven that have the provided output
!!! example
	```python
	#removes the recipe to make charcoal from the coke oven
	tweak.ie.cokeoven.remove(<minecraft:coal:1>);

	#removes all recipes from the coke oven
	tweak.ie.cokeoven.remove(*);
	```