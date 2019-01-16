#loot

Tweaks involving changing of loot tables and mob drops.

<br>

## Primer

!!! important
	It is strongly suggested you read this before editing loot tables.

<br>

### Loot Table Locations
Minecraft/Forge uses loot tables to determine what items are dropped by entities, loot chests and fishing.

Loot tables are identified by a string pointing to that tables location, for instance :  

* "minecraft:entities/zombie" : determines the loot dropped by zombies.  
* "minecraft:chests/village_blacksmith" : determines the loot generated in blacksmith chests.  

For a full list of loot tables take a look in the [glossary](/glossary/loottables/).

<br>

### Loot Table Basics
A loot table consists of one or more loot pools, a loot pool consists of one or more loot entries.  
A loot pool is used to group entries that can then be chosen between, allowing you to drop x items from each pool.  
A loot entry is used to determine the actual item that will drop.  

<br>

### Loot Pool Conditions
A loot pool can have a number of conditions attached to it, it will then only drop items if those conditions are filled.  
The current conditions are :  

* playerOnly : Successful if killed by a player, prevents drops when killed by most mob farms.  
* chance : Successful on a random percentage roll.  
* chanceWithLooting : Successful on a random percentage roll, with additional success chance with the looting enchant.  

<br>

### Loot Entry Functions
A loot entry can have a number of functions attached to it, functions can alter the behaviour of drops.
The current functions are :

* enchant : Applies a specific enchant to a drop
* enchantRandomly : Applies a random enchant to a drop
* smelt : Attempts to smelt drops if the entity is killed while on fire, similar to meat drops from animals

<br>

### Special Case - The Wither
The Wither doesn't have a normal loot table, meaning normally it cannot be edited.  
Tweaked makes a special case and allows you to specify the Withers loot table as "entities/wither".  

However, it is important to note that this essentially clears the Withers current loot, as though the clear action had been used.  
**This means that you will need to re-add Nether Stars and any drops added by other mods to the drop table**.  

<br>

---
## clear

<pre>tweak.loot.clear(<a href="/arguments/string/">string</a> key)</pre>

Clears all loot pools from loot table, essentially removing all loot.

!!! example
	```python
	#remove all loot drops from pigs
	tweak.loot.clear("minecraft:entities/pig");
	```

<br>

---
## addPool

<pre>tweak.loot.addPool(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, <a href="/arguments/integer/">integer</a> minCount, <a href="/arguments/integer/">integer</a> maxCount)</pre>
<pre>tweak.loot.addPool(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, <a href="/arguments/integer/">integer</a> minCount, <a href="/arguments/integer/">integer</a> maxCount, <a href="/arguments/integer/">integer</a> minBonus, <a href="/arguments/integer/">integer</a> maxBonus)</pre>

Adds a new loot pool to a loot table.  

* minCount : The minimum number of items that can drop from this pool.  
* maxCount : The maximum number of items that can drop from this pool.  
* minBonus : The minimum additional items that can drop based on the players luck.  
* maxBonus : The minimum additional items that can drop based on the players luck.  

!!! note
	The formula for number of items dropped is :  
	`Random(minCount, maxCount) + ( Random(minBonus, maxBonus) * playerLuck );`

!!! example
	```python
	#add a new pool to a zombie, dropping between 2 and 4 items
	tweak.loot.addPool("minecraft:entities/zombie", "tutorialPool", 2, 4);
	```
	
<br>

---
## removePool

<pre>tweak.loot.removePool(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName)</pre>

Removes a loot pool from a loot table, removing all entries within it.

!!! example
	```python
	#removes the main pool from zombies, meaning they will no longer drop rotten flesh
	tweak.loot.removePool("minecraft:entities/zombie", "main");
	```
	
<br>

---
## addEntry

<pre>tweak.loot.addEntry(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, <a href="/arguments/string/">string</a> entryName, <a href="/arguments/stack/">stack</a> stack, <a href="/arguments/integer/">integer</a> weight, <a href="/arguments/integer/">integer</a> quality)</pre>
<pre>tweak.loot.addEntry(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, <a href="/arguments/string/">string</a> entryName, <a href="/arguments/stack/">stack</a> stack, <a href="/arguments/integer/">integer</a> weight, <a href="/arguments/integer/">integer</a> quality, <a href="/arguments/integer/">integer</a> bonusMin, <a href="/arguments/integer/">integer</a> bonusMax)</pre>

Adds a new loot entry to a loot pool.  

* stack : A stack representing the item that will drop.  
* weight : The chance for this item to drop compared to others in the same pool, an entry with weight of 2 is twice as likely to drop as an entry with weight 1.  
* quality : Additional weight provided by player luck, adding ( quality * playerLuck ) to the weight.  
* bonusMin : The minimum additional items that can be dropped based on the level of looting enchant.  
* bonusMax : The maximum additional items that can be dropped based on the level of looting enchant.  

!!! example
	```python
	#add a new entry to a zombie, causing it to drop diamonds
	tweak.loot.addPool("minecraft:entities/zombie", "tutorialPool", "tutorialEntry", <minecraft:diamond>, 1, 0);
	```
	
<br>

---
## removeEntry

<pre>tweak.loot.removeEntry(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, <a href="/arguments/string/">string</a> entryName)</pre>

Removes a loot entry from a loot pool.

!!!example
	```python
	#removes the entry for string from spiders
	tweak.loot.removeEntry("minecraft:entities/spider", "main", "minecraft:string");"
	```
	
<br>

---
## addCondition

Adds a new condition to a loot pool, the action chosen depends on the type of condition you wish to add.  

### playerOnly
<pre>tweak.loot.addCondition(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, "playerOnly")</pre>
Flags the pool to only succeed when killed by a player.  

### chance
<pre>tweak.loot.addCondition(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, "chance", <a href="/arguments/float/">float</a> successChance)</pre>
Flags the pool to only succeed when passing the defined chance.  

### chanceWithLooting
<pre>tweak.loot.addCondition(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, "chanceWithLooting", <a href="/arguments/float/">float</a> successChance, <a href="/arguments/float/">float</a> bonusChance)</pre>
Flags the pool to only succeed when passing the defined chance, increased by bonusChance for each level of looting.  

!!! example
	```python
	#the pool will only generate if killed by a player
	tweak.loot.addCondition("minecraft:entities/zombie", "tutorialPool", "playerOnly");

	#the pool will only generate 40% of the time
	tweak.loot.addCondition("minecraft:entities/zombie", "tutorialPool", "chance", 0.4);

	#the pool will only generate 20% of the time, increased by 10% for each level of looting
	tweak.loot.addCondition("minecraft:entities/zombie", "tutorialPool", "chanceWithLooting", 0.2, 0.1);
	```
	
<br>

---
## addFunction

Adds a new function to a loot entry, the action chosen depends on the type of function you wish to add.  

### enchant

<pre>tweak.loot.addFunction(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, <a href="/arguments/string/">string</a> entryName, "enchant", <a href="/arguments/integer/">integer</a> minPower, <a href="/arguments/integer/">integer</a> maxPower, <a href="/arguments/boolean/">boolean</a> allowTreasure)</pre>
Flags the entry to randomly enchant the item with a random enchantment strength, treasure enchants can be enabled/disabled.

### smelt
<pre>tweak.loot.addFunction(<a href="/arguments/string/">string</a> key, <a href="/arguments/string/">string</a> poolName, <a href="/arguments/string/">string</a> entryName, "smelt")</pre>
Flags the pool to smelt the item if the entity is burning and the item can be smelted.  

!!! note
	Fixed enchants can be applied to loot using the [enchant modifier](/arguments/stack/#enchant).

!!! example
	```python
	#the entry will be enchanted randomly with a power between 20 and 30, not allowing treasure enchants
	tweak.loot.addFunction("minecraft:entities/zombie", "tutorialPool", "tutorialEntry", "enchant", 20, 30, false);

	#the entry will be smelted if the entity was burning when killed
	tweak.loot.addFunction("minecraft:entities/zombie", "tutorialPool", "tutorialEntry", "smelt");
	```
	
<br>
