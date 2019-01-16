# stack

A stack is a way to represent any item or block, including information such as metadata, item count and nbtcompounds. 

A stack is a type of [ingredient](/arguments/ingredient/) and can therefore be used in any method as one.

## Argument
Stack information is split using the `:` modifier, with each split item being referred to as a token.  
A stack can have between 2-5 tokens and the number of tokens determine what information is passed in.

<br>

### 2 Tokens - Basic Stack
<pre>&lt;mod:name&gt;</pre>

Creates a stack using the item/block registered by the provided mod and name.

!!! example
	```python
	#creates a stack of 1 diamond
	<minecraft:diamond>
	```

<br>
	
### 3 Tokens - Stack with Meta
<pre>&lt;mod:name:meta&gt;</pre>

Creates a stack using the item/block registered by the provided mod and name, using the specified meta data.

!!! note
	meta must be a parsable integer

!!! example
	```python
	#creates a stack of specific coloured wool
	<minecraft:wool:3>
	```

<br>
	
### 4 Tokens - Stack with Meta and Count
<pre>&lt;mod:name:meta:count&gt;</pre>

Creates a stack using the item/block registered by the provided mod and name, using the specified meta data and item count.

!!! note
	meta/count must be a parsable integers

!!! example
	```python
	#creates a stack of 16 diamonds
	<minecraft:diamond:0:16>
	```

<br>
	
### 5 Tokens - Stack with Meta, Count and NBTCompound
<pre>&lt;mod:name:meta:count:nbt&gt;</pre>

Creates a stack using the item/block registered by the provided mod and name, using the specified meta data, item count and nbt compound.

!!! note
	meta/count must be a parsable integers, nbt must be a valid nbt string 

!!! example
	```python
	#creates a stack of a forge bucket, filled with immersive engineering liquid concrete
	<forge:bucketfilled:0:1:{FluidName: "concrete", Amount: 1000}>
	```
<br>

---
## Variable

A Stack can also be stored as a variable, the argument can be any of those specified above.	

!!! example
	```python
	#creates a variable assigned to a diamond stack
	$varStack = stack(<minecraft:diamond>);
	```

<br>

---
## Modifiers

Modifiers allow additional information to be added to a Stack after it has been created.

They are specified using the syntax `.modifer{ arguments }`.

!!! note
	Multiple modifiers can be added by simply adding them after each other.
	
<br>

### enchant
<pre>.enchant{enchantment:level}</pre>

Applies a specified enchantment to the stack.

A list of enchantments can be found [here](/glossary/enchantments/).

!!! example
	```python
	#creates a diamond sword with the sharpness enchant
	<minecraft:diamond_sword>.enchant{minecraft:sharpness:5}
	```