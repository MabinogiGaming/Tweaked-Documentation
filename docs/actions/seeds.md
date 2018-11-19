#seeds

Tweaks involving changing of seeds dropped when destroying tall grass.

<br>

---
## add

**tweak.seeds.add([stack](/arguments/stack/) seed, [integer](/arguments/integer/) weight)**  

Adds a seed to the drop table with a specified weight.
Seeds are chosen by comparing weights to each other, as reference vanilla seeds have a weight of 10.

!!! example
	```python
	#add diamonds to seed drops, 10% as likely as normal seeds
	tweak.seeds.add(<minecraft:diamond>, 1);
	```

<br>

---
## remove

**tweak.seeds.remove([all](/arguments/all/) all)**  
**tweak.seeds.remove([stack](/arguments/stack/) seed)**  

Remove all or a specified seed drop, preventing it from dropping from tall grass.

!!! example
	```python
	#disable the vanilla seed drop
	tweak.seeds.remove(<minecraft:wheat_seeds>);
	```

<br>