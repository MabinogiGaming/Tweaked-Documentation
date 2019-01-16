#furnace

Tweaks involving changing of Vanilla furnace recipes and fuels.

<br>

---
## add

<pre>tweak.furnace.add(<a href="/arguments/stack/">stack</a> input, <a href="/arguments/stack/">stack</a> output)</pre>
<pre>tweak.furnace.add(<a href="/arguments/stack/">stack</a> input, <a href="/arguments/stack/">stack</a> output, <a href="/arguments/float/">float</a> experience)</pre>

Adds a recipe to the furnace with the option to specify the experience dropped.

!!! example
	```python
	#add recipe to turn coal into diamonds
	tweak.furnace.add(<minecraft:coal>, <minecraft:diamond>, 4.0);
	```

<br>

---
## remove

<pre>tweak.furnace.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.furnace.remove(<a href="/arguments/stack/">stack</a> output)</pre>

Remove all or a recipe specified by its output.

!!! example
	```python
	#disable the vanilla stone recipe
	tweak.furnace.remove(<minecraft:stone>);
	```

<br>

---
## addfuel

<pre>tweak.furnace.addFuel(<a href="/arguments/stack/">stack</a> fuel, <a href="/arguments/integer/">integer</a> burnTime)</pre>

Adds a new fuel type, burning for the specified time.

!!! example
	```python
	#add diamonds as a fuel, burning 10 times longer than coal
	tweak.furnace.addfuel(<minecraft:diamond>, 8000);
	```

<br>

---
## removefuel

<pre>tweak.furnace.removeFuel(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.furnace.removeFuel(<a href="/arguments/stack/">stack</a> output)</pre>

Removes all or a specified fuel.

!!! example
	```python
	#remove coal as a fuel.
	tweak.furnace.removefuel(<minecraft:coal>);
	```

<br>