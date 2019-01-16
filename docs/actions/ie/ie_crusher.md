#ie.crusher

Tweaks involving the Crusher from Immersive Engineering.

<br>

---
## add

<pre>tweak.ie.crusher.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/integer/">integer</a> time)</pre>
<pre>tweak.ie.crusher.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/dict/">dict</a> input, <a href="/arguments/integer/">integer</a> time)</pre>

Adds a new recipe to the crusher.

!!! example
	```python
	#adds recipe where stone turns into diamonds, taking 1000 ticks
	tweak.ie.crusher.add(<minecraft:diamond>, <minecraft:stone>, 1000);
	```
<br>

---
## remove

<pre>tweak.ie.crusher.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.ie.crusher.remove(<a href="/arguments/stack/">stack</a> output)</pre>
<pre>tweak.ie.crusher.remove(<a href="/arguments/stacklist/">stacklist</a> outputs)</pre>

Removes all recipes from the crusher that have the provided output

!!! example
	```python
	#removes any recipes to make diamond from the crusher
	tweak.ie.crusher.remove(<minecraft:diamond>);

	#removes all recipes from the crusher
	tweak.ie.crusher.remove(*);
	```