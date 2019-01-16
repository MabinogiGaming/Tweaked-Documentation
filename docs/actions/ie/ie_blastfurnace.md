#ie.blastfurnace

Tweaks involving the Blast Furnace from Immersive Engineering.

<br>

---
## add

<pre>tweak.ie.blastfurnace.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/integer/">integer</a> time)</pre>
<pre>tweak.ie.blastfurnace.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/integer/">integer</a> time, <a href="/arguments/stack/">stack</a> slag)</pre>
<pre>tweak.ie.blastfurnace.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/dict/">dict</a> input, <a href="/arguments/integer/">integer</a> time)</pre>
<pre>tweak.ie.blastfurnace.add(<a href="/arguments/stack/">stack</a> output, <a href="/arguments/dict/">dict</a> input, <a href="/arguments/integer/">integer</a> time, <a href="/arguments/stack/">stack</a> slag)</pre>

Adds a new recipe to the blast furnace.

!!! example
	```python
	#adds recipe where stone turns into diamonds and produces coal as slag, taking 1000 ticks
	tweak.ie.blastfurnace.add(<minecraft:diamond>, <minecraft:stone>, 1000, <minecraft:coal>);
	```
<br>

---
## remove

<pre>tweak.ie.blastfurnace.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.ie.blastfurnace.remove(<a href="/arguments/stack/">stack</a> output)</pre>
<pre>tweak.ie.blastfurnace.remove(<a href="/arguments/stacklist/">stacklist</a> outputs)</pre>

Removes all recipes from the blast furnace that have the provided output.

!!! example
	```python
	#removes a recipe to make coal from the blast furnace
	tweak.ie.blastfurnace.remove(<minecraft:coal>);

	#removes all recipes from the blast furnace
	tweak.ie.blastfurnace.remove(*);
	```
<br>

---
## addFuel

<pre>tweak.ie.blastfurnace.addFuel(<a href="/arguments/stack/">stack</a> fuel, <a href="/arguments/integer/">integer</a> time)</pre>
<pre>tweak.ie.blastfurnace.addFuel(<a href="/arguments/dict/">dict</a> fuel, <a href="/arguments/integer/">integer</a> time)</pre>

Adds a new fuel to the blast furnace.

!!! example
	```python
	#adds diamonds as a fuel type that burn for 1000 ticks
	tweak.ie.blastfurnace.addFuel(<minecraft:diamond>, 1000);
	```
<br>

---
## removeFuel

<pre>tweak.ie.blastfurnace.removeFuel(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.ie.blastfurnace.removeFuel(<a href="/arguments/stack/">stack</a> fuel)</pre>
<pre>tweak.ie.blastfurnace.removeFuel(<a href="/arguments/stacklist/">stacklist</a> fuels)</pre>

Removes any matching fuels from the blast furnace.

!!! example
	```python
	#removes a charcoal as a fuel from the blast furnace
	tweak.ie.blastfurnace.removeFuel(<minecraft:charcoal>);

	#removes all fuels from the blast furnace
	tweak.ie.blastfurnace.removeFuel(*);
	```