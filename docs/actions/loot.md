#loot

Tweaks involving changing of loot tables and mob drops.

<br>

## Primer
It is strongly suggested you read this before editting loot tables.

<br>

### Loot Table Locations
Minecraft/Forge uses loot tables to determine what items are dropped by entities, loot chests and fishing.

Loot tables are identified by a string pointing to that tables location, for instance :  

* "entities/zombie" : determines the loot dropped by zombies.  
* "chests/village_blacksmith" : determines the loot generated in blacksmith chests.  

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
A loot entry can have a number of functions attached to it, functions can altar the behaviour of drops.
The current functions are :

* enchant : Applies a specific enchant to a drop
* enchantRandomly : Applies a random enchant to a drop
* smelt : Attempts to smelt drops if the entity is killed while on fire, similar to meat drops from animals

<br>

### Special Case - The Wither
The Wither doesn't have a normal loot table, meaning normally it cannot be editted.  
Tweaked makes a special case and allows you to specify the Withers loot table as "entities/wither".  

However, it is important to note that this essentially clears the Withers current loot, as though the clear action had been used.  
**This means that you will need to re-add Nether Stars and any drops added by other mods to the drop table**.  

<br>

---
## clear

*tweak.loot.clear([string](/arguments/string/) key)*  

Clears all loot pools from loot table, essentially removing all loot.
```python
#remove all loot drops from pigs
tweak.loot.clear("entity/pig");
```
<br>

---
## addPool

*tweak.loot.addPool([string](/arguments/string/) key, [string](/arguments/string/) poolName, [integer](/arguments/integer/) minCount, [integer](/arguments/integer/) maxCount)*  
*tweak.loot.addPool([string](/arguments/string/) key, [string](/arguments/string/) poolName, [integer](/arguments/integer/) minCount, [integer](/arguments/integer/) maxCount, [integer](/arguments/integer/) minBonus, [integer](/arguments/integer/) maxBonus)*  

Adds a new loot pool to a loot table.  

* minCount : The minimum number of items that can drop from this pool.  
* maxCount : The maximum number of items that can drop from this pool.  
* minBonus : The minimum additional items that can drop based on the players luck.  
* maxBonus : The minimum additional items that can drop based on the players luck.  

The formula for number of items dropped is :  
`Random(minCount, maxCount) + ( Random(minBonus, maxBonus) * playerLuck );`

```python
#add a new pool to a zombie, dropping between 2 and 4 items
tweak.loot.addPool("entity/zombie", "tutorialPool", 2, 4);
```
<br>

---
## removePool

*tweak.loot.removePool([string](/arguments/string/) key, [string](/arguments/string/) poolName)*  

Removes a loot pool from a loot table, removing all entries within it.
```python
#removes the main pool from zombies, meaning they will no longer drop rotten flesh
tweak.loot.removePool("entity/zombie", "main");
```
<br>

---
## addEntry

*tweak.loot.addEntry([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, [stack](/arguments/stack/) stack, [integer](/arguments/integer/) weight, [integer](/arguments/integer/) quality)*  
*tweak.loot.addEntry([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, [stack](/arguments/stack/) stack, [integer](/arguments/integer/) weight, [integer](/arguments/integer/) quality, [integer](/arguments/integer/) bonusMin, [integer](/arguments/integer/) bonusMax)*  

Adds a new loot entry to a loot pool.  

* stack : A stack representing the item that will drop.  
* weight : The chance for this item to drop compared to others in the same pool, an entry with weight of 2 is twice as likely to drop as an entry with weight 1.  
* quality : Additional weight provided by player luck, adding ( quality * playerLuck ) to the weight.  
* bonusMin : The minimum additional items that can be dropped based on the level of looting enchant.  
* bonusMax : The maximum additional items that can be dropped based on the level of looting enchant.  
```python
#add a new entry to a zombie, causing it to drop diamonds
tweak.loot.addPool("entity/zombie", "tutorialPool", "tutorialEntry", <minecraft:diamond>, 1, 0);
```
<br>

---
## removeEntry

*tweak.loot.removeEntry([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName)*  

Removes a loot entry from a loot pool.
```python
#removes the entry for string from spiders
tweak.loot.removeEntry("entities/spider", "main", "minecraft:string");"
```
<br>

---
## addCondition

*tweak.loot.addCondition([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) value)*  
*tweak.loot.addCondition([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) value, [float](/arguments/float/) inputA)*  
*tweak.loot.addCondition([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) value, [float](/arguments/float/) inputA, [float](/arguments/float/) inputB)*  

Adds a new condition to a loot pool, the action chosen depends on the type of condition you wish to add.  

### playerOnly
*tweak.loot.addCondition([string](/arguments/string/) key, [string](/arguments/string/) poolName, "playerOnly")*  
Flags the pool to only succeed when killed by a player.  

### chance
*tweak.loot.addCondition([string](/arguments/string/) key, [string](/arguments/string/) poolName, "chance", [float](/arguments/float/) succeedChance)*  
Flags the pool to only succeed when passing the defined chance.  

### chanceWithLooting
*tweak.loot.addCondition([string](/arguments/string/) key, [string](/arguments/string/) poolName, "chanceWithLooting", [float](/arguments/float/) succeedChance, [float](/arguments/float/) bonusChance)*  
Flags the pool to only succeed when passing the defined chance, increased by bonusChance for each level of looting.  

```python
#the pool will only generate if killed by a player
tweak.loot.addCondition("entity/zombie", "tutorialPool", "playerOnly");

#the pool will only generate 40% of the time
tweak.loot.addCondition("entity/zombie", "tutorialPool", "chance", 0.4);

#the pool will only generate 20% of the time, increased by 10% for each level of looting
tweak.loot.addCondition("entity/zombie", "tutorialPool", "chanceWithLooting", 0.2, 0.1);
```
<br>

---
## addFunction

*tweak.loot.addFunction([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, [string](/arguments/string/) value)*  
*tweak.loot.addFunction([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, [string](/arguments/string/) value, [string](/arguments/string/) inputA, [integer](/arguments/integer/) inputB)*  
*tweak.loot.addFunction([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, [string](/arguments/string/) value, [integer](/arguments/integer/) inputA, [integer](/arguments/integer/) inputB, [boolean](/arguments/boolean/) inputC)*  

Adds a new function to a loot entry, the action chosen depends on the type of function you wish to add.  

### enchant
*tweak.loot.addFunction([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, "enchant", [string](/arguments/string/) enchantName, [integer](/arguments/integer/) enchantLevel)*  
Flags the entry to enchant the item with the specified enchant and level.  
Multiple enchants can be applied to a single entry.  
For a full list of enchantments take a look in the [glossary](/glossary/enchantments/).  

### enchantRandomly
*tweak.loot.addFunction([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, "enchantRandomly", [integer](/arguments/integer/) minPower, [integer](/arguments/integer/) maxPower, [boolean](/arguments/boolean/) allowTreasure)*  
Flags the entry to randomly enchant the item with a random enchantment strength, treasure enchants can be enabled/disabled.

### smelt
*tweak.loot.addFunction([string](/arguments/string/) key, [string](/arguments/string/) poolName, [string](/arguments/string/) entryName, "smelt")*  
Flags the pool to smelt the item if the entity is burning and the item can be smelted.  

```python
#the entry will be enchanted with Sharpness III
tweak.loot.addFunction("entity/zombie", "tutorialPool", "tutorialEntry", "enchant", "sharpness", 3);

#the entry will be enchanted randomly with a power between 20 and 30, not allowing treasure enchants
tweak.loot.addFunction("entity/zombie", "tutorialPool", "tutorialEntry", "enchantRandomly", 20, 30, false);

#the entry will be smelted if the entity was burning when killed
tweak.loot.addFunction("entity/zombie", "tutorialPool", "tutorialEntry", "smelt");
```
<br>
