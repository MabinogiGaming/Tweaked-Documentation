#furnace

Tweaks involving changing of Vanilla furnace recipes and fuels.

<br>

---
## add

**tweak.furnace.add([stack](/arguments/stack/) input, [stack](/arguments/stack/) output)**  
**tweak.furnace.add([stack](/arguments/stack/) input, [stack](/arguments/stack/) output, [float](/arguments/float/) experience)**  

Adds a recipe to the furnace with the option to specify the experience dropped.

!!! example
	```python
	#add recipe to turn coal into diamonds
	tweak.furnace.add(<minecraft:coal>, <minecraft:diamond>, 4.0);
	```

<br>

---
## remove

**tweak.furnace.remove([all](/arguments/all/) all)**  
**tweak.furnace.remove([stack](/arguments/stack/) output)**  

Remove all or a recipe specified by its output.

!!! example
	```python
	#disable the vanilla stone recipe
	tweak.furnace.remove(<minecraft:stone>);
	```

<br>

---
## addfuel

**tweak.furnace.addFuel([stack](/arguments/stack/) fuel, [integer](/arguments/integer/) burnTime)**  

Adds a new fuel type, burning for the specified time.

!!! example
	```python
	#add diamonds as a fuel, burning 10 times longer than coal
	tweak.furnace.addfuel(<minecraft:diamond>, 8000);
	```

<br>

---
## removefuel

**tweak.furnace.removeFuel([all](/arguments/all/) all)**  
**tweak.furnace.removeFuel([stack](/arguments/stack/) fuel)**  

Removes all or a specified fuel.

!!! example
	```python
	#remove coal as a fuel.
	tweak.furnace.removefuel(<minecraft:coal>);
	```

<br>