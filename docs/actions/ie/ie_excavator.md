#ie.excavator

Tweaks involving the Excavator from Immersive Engineering.

<br>

---
## add

<pre>tweak.ie.excavator.add(<a href="/arguments/string/">string</a> name, <a href="/arguments/integer/">integer</a> weight, <a href="/arguments/float/">float</a> failChance, <a href="/arguments/string/">string</a> oreName, <a href="/arguments/float/">float</a> chance)</pre>

Adds a mineral mix to the excavator.

!!! example
	```python
	#adds a mineral mix that gives Iron, with weight 25 and a fail chance of 10%
	tweak.ie.excavator.add("Pure Iron", 25, 0.1, "oreIron", 1.0);
	```
<br>

---
## remove

<pre>tweak.ie.excavator.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.ie.excavator.remove(<a href="/arguments/string/">string</a> name)</pre>

Removes all mineral mix from the Excavator that have the provided name.
!!! example
	```python
	#removes the Silver mineral mix
	tweak.ie.excavator.remove("Silver");

	#removes all mineral mixes
	tweak.ie.excavator.remove(*);
	```