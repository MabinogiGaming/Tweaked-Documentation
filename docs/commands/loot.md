# loot

Provides debugging abilities related to loot drop tables.

<br>

---
## loot

<pre>/tweaked loot [loottable]</pre>
<pre>/tweaked loot [loottable] [count]</pre>

Generates loot as though you had killed/opened the specified loottable and throws the items on the ground.

Specifying a count allows you to run the operation multiple times.

For a full list of loot tables take a look in the [glossary](/glossary/loottables/).

!!! note

    The loot will be generated as though killed/found by the player using the command, using the item in the players main hand.  
	This means that you can use luck potions/looting weapons to simulate specific conditions.

!!! example
	
	```python
	#generates loot for a blacksmiths chest
	/tweaked loot chests/village_blacksmith

	#generates loot for 10 zombies
	/tweaked loot entities/zombie 10
	```