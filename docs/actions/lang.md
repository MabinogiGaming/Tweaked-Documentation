#lang

Tweaks involving language files and translations.

<br>

---

## set

**tweak.lang.set([string](/arguments/string/) string, [string](/arguments/string/) name)**  
**tweak.lang.set([stack](/arguments/stack/) stack, [string](/arguments/string/) name)**

Sets the translated name for the provided string/item/block, overriding the normal one.

!!!example
	```python
	#change the name of a villager
	tweak.lang.setName("entity.Villager.fisherman", "Fish Master");

	#change the name of diamond to tweaked
	tweak.lang.setName(<minecraft:diamond>, "tweaked");
	```