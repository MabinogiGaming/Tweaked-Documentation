#dict

Tweaks involving changing of the OreDictionary and its contents.

Items that are registered to the OreDictionary become interchangeable with other items that have the same OreDictionary name. This allows recipes to use either item to produce the same result.

<br>

---
## add

**tweak.dict.add([string](/arguments/string/) oreName, [stack](/arguments/stack/) stack)**  

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

**tweak.dict.remove([string](/arguments/string/) oreName, [stack](/arguments/stack/) stack)**  

Removes the specified stack from the oreName dictionary.

!!! example
	```python
	#removes the ability to use spruce planks in recipes such as a crafting table
	tweak.dict.remove("plankWood", <minecraft:plank:1>);
	```

<br>

---
## replace

**tweak.dict.replace([string](/arguments/string/) oreName, [stack](/arguments/stack/) stack)**  

Replaces all current stacks in the oreName dictionary with the specified stack.

!!! example
	```python
	#removes the ability to use any planks other than oak in recipes such as the crafting table
	tweak.dict.replace("plankWood", <minecraft:plank:0>);
	```

<br>