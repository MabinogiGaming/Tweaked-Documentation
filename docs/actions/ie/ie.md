#ie

Tweaks involving the mod Immersive Engineering.

<br>

---
## disableMultiblock

<pre>tweak.ie.disableMultiblock(<a href="/arguments/all/">all</a> *)</pre>
<pre>tweak.ie.disableMultiblock(<a href="/arguments/string/">string</a> name)</pre>
<pre>tweak.ie.disableMultiblock(<a href="/arguments/stringlist/">stringlist</a> names)</pre>

Prevents the specified multiblock from forming when hit with an engineers hammer.

For a full list of multiblocks take a look in the [glossary](/glossary/multiblocks/). 

!!! example
	```python
	#disable the crusher
	tweak.ie.disableMultiblock("IE:Crusher");

	#disable all multiblocks
	tweak.ie.disableMultiblock(*);
	```