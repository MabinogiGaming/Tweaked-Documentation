#ie

Tweaks involving the mod Immersive Engineering.

## disableMultiblock
*tweak.ie.disableMultiblock([string](/arguments/string/) name);*  
*tweak.ie.disableMultiblock([stringList](/arguments/stringlist/) names);*  
*tweak.ie.disableMultiblock([all](/arguments/all/) all);*

Prevents the specified multiblock from forming when hit with an engineers hammer.

For a full list of multiblocks take a look in the [glossary](/glossary/multiblocks/). 

```python
#disable the crusher
tweak.ie.disableMultiblock("IE:Crusher");

#disable all multiblocks
tweak.ie.disableMultiblock(*);
```