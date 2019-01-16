#seeds

Tweaks involving changing of seeds dropped when destroying tall grass.

<br>

---
## add

<pre>tweak.seeds.add(<a href="/arguments/stack/">stack</a> seed, <a href="/arguments/integer/">integer</a> weight)</pre>

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

<pre>tweak.seeds.remove(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.seeds.remove(<a href="/arguments/stack/">stack</a> seed)</pre>

Remove all or a specified seed drop, preventing it from dropping from tall grass.

!!! example
	```python
	#disable the vanilla seed drop
	tweak.seeds.remove(<minecraft:wheat_seeds>);
	```

<br>