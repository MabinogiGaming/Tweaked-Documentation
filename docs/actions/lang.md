#lang

Tweaks involving language files and translations.

<br>

---

## set

<pre>tweak.lang.set(<a href="/arguments/string/">string</a> string, <a href="/arguments/string/">string</a> name)</pre>
<pre>tweak.lang.set(<a href="/arguments/stack/">stack</a> stack, <a href="/arguments/string/">string</a> name)</pre>

Sets the translated name for the provided string/stack, overriding the normal one.

!!!example
	```python
	#change the name of a villager
	tweak.lang.setName("entity.Villager.fisherman", "Fish Master");

	#change the name of diamond to tweaked
	tweak.lang.setName(<minecraft:diamond>, "tweaked");
	```