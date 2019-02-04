# Your First Script

This is a short tutorial that will take you through some of the basics of scripting.

<br>

---
## Creating the script file

Create a new file named `test.tweak` inside the `/Tweaked/Scripts` directory

For this example we will print a message to the log file. `print` is a special action that we can use to do this.

Inside `test.tweak` paste the following code :  
```
print("Test Message");
```

Now run minecraft and once it's loaded look inside the `tweaked.log` file. You should see that your script has output the specified message.

<br>

---
## Modifying crafting recipes

Next, lets try modifying some default recipes.

We will change the amount of torches in the vanilla torch recipe to give 16 torches rather than 4.

First we will need to remove the default torch recipe, add the following code :
```python
tweak.recipes.remove("minecraft:torch");
```

And now we can add the replacement recipe, add the following code :
```python
tweak.recipes.shaped("bonus_torch", <minecraft:torch:0:16>, [[<minecraft:coal>][<stickWood>]]);
```

<img src="/img/crafting.png/">

![](/img/crafting.png/)

<br>

---
## Adding a furnace recipe

Next, lets try adding a new furnace recipe.

We will allow Diamonds to be smelted in a furnace in order to produce Bedrock, giving the player 4 XP for each craft.

Add the following code :
```python
tweak.furnace.add(<minecraft:diamond>, <minecraft:bedrock>, 4.0);
```

![](/img/furnace.png/)

<br>

---
## Renaming an item

As a finishing touch, lets change the name of bedrock to be Seared Diamond, to better fit our furnace recipe.

Add the following code :
```python
tweak.lang.set(<minecraft:bedrock>, "Seared Diamond");
```

![](/img/rename.png/)