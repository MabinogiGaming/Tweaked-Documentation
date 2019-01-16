#dict

Tweaks involving changing of the OreDictionary and its contents.

Items that are registered to the OreDictionary become interchangeable with other items that have the same OreDictionary name. This allows recipes to use either item to produce the same result.

<br>

---
## add

<pre>tweak.dict.add(<a href="/arguments/string/">string</a> oreName, <a href="/arguments/stack/">stack</a> stack)</pre>

Assigns the specified stack to the oreName dictionary.

!!! note

	Forge uses a wildcard meta value of 30000 to allow specifying all metadatas of an item.
	For instance <minecraft:plank:30000> will allow all metas (oak, spruce, ..) to be accepted.

!!! example
	```python
	#allow cobblestone to be used in place of stone as part of the ore dictionary
	tweak.dict.add("stone", <minecraft:cobblestone>);
	```

<br>

---
## remove

<pre>tweak.dict.remove(<a href="/arguments/string/">string</a> oreName, <a href="/arguments/stack/">stack</a> stack)</pre>

Removes the specified stack from the oreName dictionary.

!!! example
	```python
	#removes the ability to use spruce planks in recipes such as a crafting table
	tweak.dict.remove("plankWood", <minecraft:plank:1>);
	```

<br>

---
## replace

<pre>tweak.dict.replace(<a href="/arguments/string/">string</a> oreName, <a href="/arguments/stack/">stack</a> stack)</pre>

Replaces all current stacks in the oreName dictionary with the specified stack.

!!! example
	```python
	#removes the ability to use any planks other than oak in recipes such as the crafting table
	tweak.dict.replace("plankWood", <minecraft:plank:0>);
	```

<br>