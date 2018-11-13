# dict

!!! note

	Forge uses a wildcard meta value of 30000 to allow specifying all metadatas of an item.
	For instance <minecraft:plank:30000> will allow all metas (oak, spruce, ..) to be accepted.
	
<br>

---

**/tweaked dict**

Prints a list of all [dicts](/arguments/dict/) associated to the currently held item to chat.

The printed text can be clicked to copy to the clipboard.

!!! example
	```python
	#while holding a crafting table in the main hand

	/tweaked dict
		<workbench>
		<craftingTableWood>
	```

<br>

---

<br>

**/tweaked dict [dictName]**

Prints a list of all [stacks](/arguments/stack/) associated to the specified dictionary.

The printed text can be clicked to copy to the clipboard.

!!! example
	```python
	/tweaked dict stone
		<minecraft:stone>
	```