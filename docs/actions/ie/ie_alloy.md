#ie.alloy

Tweaks involving the **Alloy Kiln** from Immersive Engineering.

<br>

---
## add

<pre>tweak.ie.alloy.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/stack/">stack</a> inputA, <a href="/arguments/stack/">stack</a> inputB, <a href="/arguments/integer/">integer</a> time)</pre>
<pre>tweak.ie.alloy.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/stack/">stack</a> inputA, <a href="/arguments/dict/">dict</a> inputB, <a href="/arguments/integer/">integer</a> time)</pre>
<pre>tweak.ie.alloy.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/dict/">dict</a> inputA, <a href="/arguments/dict/">dict</a> inputB, <a href="/arguments/integer/">integer</a> time)</pre>

Adds a new recipe to the **Alloy Kiln**.

!!! example
	```python
	#adds recipe where stone and iron turns into diamonds, taking 1000 ticks
	tweak.ie.alloy.add(<minecraft:diamond>, <minecraft:stone>, <ingotIron>, 1000);
	```
<br>

---
## remove

<pre>tweak.ie.alloy.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.ie.alloy.remove(<a href="/arguments/stack/">stack</a> output)</pre>
<pre>tweak.ie.alloy.remove(<a href="/arguments/stacklist/">stacklist</a> outputs)</pre>

Removes all recipes from the **Alloy Kiln** that have the provided output

!!! example
	```python
	#removes the recipe to make charcoal from the alloy kiln
	tweak.ie.alloy.remove(<minecraft:coal:1>);

	#removes all recipes from the alloy kiln
	tweak.ie.alloy.remove(*);
	```