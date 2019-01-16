#jei

Tweaks involving the mod Just Enough Items.

<br>

---
## add

<pre>tweak.jei.add(<a href="/arguments/stack/">stack</a> stack)</pre>

Adds an item to JEI, can be useful for items that are hidden by default.

!!! example
	```python
	#adds diamond to jei
	tweak.jei.add(<minecraft:diamond>);
	```
	
<br>

---
## hide

<pre>tweak.jei.hide(<a href="/arguments/stack/">stack</a> stack)</pre>

Hides an item from jei.

!!! example
	```python
	#hides diamond in jei
	tweak.jei.hide(<minecraft:diamond>);
	```
	
<br>

---
## addInfo

<pre>tweak.jei.addInfo(<a href="/arguments/stack/">stack</a> stack, <a href="/arguments/string/">string</a> info)</pre>

Adds text to the information page for the specified stack.

!!! example
	```python
	#Adds an information to diamonds
	tweak.jei.addInfo(<minecraft:diamond>, "Information on diamonds goes here");
	```
	
<br>