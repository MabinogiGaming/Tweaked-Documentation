#jei

Tweaks involving the mod Just Enough Items.

<br>

---
## add
*tweak.jei.add([stack](/arguments/stack/) item);*

Adds an item to JEI, can be useful for items that are hidden by default.

!!! example
	```python
	#adds diamond to jei
	tweak.jei.add(<minecraft:diamond>);
	```
	
<br>

---
## hide
*tweak.jei.hide([stack](/arguments/stack/) item);*

Hides an item from jei.

!!! example
	```python
	#hides diamond in jei
	tweak.jei.hide(<minecraft:diamond>);
	```
	
<br>

---
## addInfo
*tweak.jei.addInfo([stack](/arguments/stack/) item, [string](/arguments/string/) string);*

Adds text to the information page for the specified stack.

!!! example
	```python
	#Adds an information to diamonds
	tweak.jei.addInfo(<minecraft:diamond>, "Information on diamonds goes here");
	```
	
<br>