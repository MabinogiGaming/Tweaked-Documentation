#trade

Tweaks involving changing of villagers and their trade recipes.

<br>

## Primer

### Villager Professions and Careers
Minecraft/Forge assigns villagers to professions and careers.

A profession can contain any number of careers, it is defined by a resource location, e.g :  

* **minecraft:farmer** : the farmer profession.  
* **immersiveengineering:engineer** : the engineer profession added by Immersive Engineering.  

When a Villager is created, they are randomly assigned one of the careers within his profession.  
Their Career determines their name and what trades they have available.

Careers are defined using the profession follow by a forward slash and the career name e.g :  

* **minecraft:farmer/fisherman** : the fisherman career within the farmer profession.  
* **minecraft:farmer/shepherd** : the shepherd career within the farmer profession.  

!!! note
	The [trade command](/commands/trade/) can be used to generate a full list of professions, careers and trades.
	
<br>
	
### Trade Levels
Each villager trade has an associated level, new villagers only allow access to level 1 trades  

As the player trades with a villager, higher level trades will become available.

More information can be found on the official site [here](https://minecraft.gamepedia.com/Trading).

<br>

---

## setName

<pre>tweak.trade.setName(<a href="/arguments/string/">string</a> career, <a href="/arguments/string/">string</a> name)</pre>

Changes the name of the villager, creating the untranslated format of : entity.Villager.name.

!!! note
	This is done after any other trade commands, meaning the old name should be used for them.
	
!!! note
	This will usually be accompanied by a translation using [translate](/actions/lang/#translate).

!!! example
	```python
	#change the name of the farmer to farmlord
	tweak.trade.setName("minecraft:farmer/farmer", "farmlord");
	```

<br>

---

## clear

<pre>tweak.trade.clear(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.trade.clear(<a href="/arguments/string/">string</a> career)</pre>
<pre>tweak.trade.clear(<a href="/arguments/stringlist/">stringlist</a> careers)</pre>

Clears the trades of all/provided careers, meaning they will not talk to the player unless trades are added manually.

!!! example
	```python
	#clear all trades from all careers, essentially a blank slate
	tweak.trade.clear(*);
	
	#clear all trades from the fisherman career
	tweak.trade.clear("minecraft:farmer/fisherman");
	```

<br>

---

## addCareer

<pre>tweak.trade.addCareer(<a href="/arguments/string/">string</a> profession, <a href="/arguments/string/">string</a> career)</pre>

Adds a new career to a profession.

!!! note
	This will usually be accompanied by a translation using [translate](/actions/lang/#translate/).

!!! example
	```python
	#creates the new botanist career as part of the farmer profession
	tweak.trade.addCareer("minecraft:farmer", "botanist");
	```

<br>

---

## addTrade

<pre>tweak.trade.addTrade(<a href="/arguments/string/">string</a> career, <a href="/arguments/integer/">integer</a> level, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/stack/">stack</a> output)</pre>
<pre>tweak.trade.addTrade(<a href="/arguments/string/">string</a> career, <a href="/arguments/integer/">integer</a> level, <a href="/arguments/stack/">stack</a> inputA, <a href="/arguments/stack/">stack</a> inputB, <a href="/arguments/stack/">stack</a> output)</pre>

Creates a new villager trade assigned to the specific career and level.

Can trade 1 or 2 items for any output.

!!! example
	```python
	#adds a level 2 trade to the farmer that buys 1 diamond for 3 emeralds
	tweak.trade.addTrade("minecraft:farmer/farmer", 2, <minecraft:diamond>, <minecraft:emerald:0:3>);
	```

<br>

---

## addTradeEnchant

<pre>tweak.trade.addTradeEnchant(<a href="/arguments/string/">string</a> career, <a href="/arguments/integer/">integer</a> level, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/stack/">stack</a> output, <a href="/arguments/integer/">integer</a> minPower, <a href="/arguments/integer/">integer</a> maxPower, <a href="/arguments/boolean/">boolean</a> allowTreasure)</pre>

Creates a new villager trade assigned to the specific career and level.

Trades an input for an output that is randomly enchanted using the specified min/max power values.

!!! note
	Fixed enchants can be applied to items using the [enchant modifier](/arguments/stack/#enchant).
	
!!! example
	```python
	#adds a level 3 trade to the weapon smith that sells an enchanted diamond sword for 8 emeralds
	tweak.trade.addTrade("minecraft:smith/weapon", 3, <minecraft:emerald:0:8>, <minecraft:diamond_sword>, 10, 30, false);
	```

<br>

---

## addTradeMap

<pre>tweak.trade.addTradeMap(<a href="/arguments/string/">string</a> career, <a href="/arguments/integer/">integer</a> level, <a href="/arguments/stack/">stack</a> input, <a href="/arguments/string/">string</a> mapName)</pre>
<pre>tweak.trade.addTradeMap(<a href="/arguments/string/">string</a> career, <a href="/arguments/integer/">integer</a> level, <a href="/arguments/stack/">stack</a> inputA, <a href="/arguments/stack/">stack</a> inputB, <a href="/arguments/string/">string</a> mapName)</pre>

Creates a new villager trade assigned to the specific career and level.

Trades 1 or 2 items for a map to a specified location. Valid map types can be found [here](/glossary/maps/).

!!! example
	```python
	#adds a level 1 trade to the cartographer that sells a map to the ocean monument for 1 emerald
	tweak.trade.addTradeMap("minecraft:librarian/cartographer", 1, <minecraft:emerald>, "monument");
	```

<br>