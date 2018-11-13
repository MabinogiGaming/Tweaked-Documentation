# Getting Started

Upon running minecraft for the first time, **Tweaked** will created a new folder in the base directory called `/Tweaked`.

Inside that folder you will find a number of files/directories :  

* `tweaked.cfg` = Configuration file, this allows you to change the way **Tweaked** behaves.
* `tweaked.log` = Log file, information or warnings are output here.
* `tweaked.dump` = Dump file, any ingame commands output here.
* `scripts` = A directory containing scripts (see below).

<br>

---
## Commands

`Commands` are chat commands that the user can input while ingame in order to help creating scripts.

The syntax for a command is `/tweaked command arguments`, e.g :

```python
# This command will print registry information on the currently held item
/tweaked hand
```

`Hint : tweaked can be shortened to just the letter t, e.g : /t hand`

<br>

---
## Scripts

Upon starting minecraft, **Tweaked** searches the `/Tweaked/Scripts` directory (including subdirectories) for scripts to load.

For a script to be loaded it must have the file type `.tweak`.

All scripts are loaded at the `ModConstruction` phase of minecraft, they are then deployed at the correct time by Tweaked.

<br>

---
### Basic Scripting

Scripts consist of a number of `Actions`. These tell **Tweaked** what to do.

`Actions` are provided with `Arguments` that allow the user to pass in information.

The full syntax for an action is : `tweak.<action>(<arguments);`, e.g :

```python
# This action will remove the recipe specific by "recipeName"
tweak.recipes.remove("recipeName");
```

`Variables` can be used to store `Arguments`, allowing them to be used in `Methods`, e.g :

`Variables` have the syntax `$<variable name> = <variable type>(<arguments>);

```python
# This does exactly the same as the previous example, except using a variable.
$testVar = String("recipeName");
tweak.recipes.remove($testVar);
```

!!! note

	tweak can be written as either `tweak.`, `tweaked.` or simply `.`, all have the same effect.
	
!!! note

	Actions and Variables are case insensitive, `addrecipe`, `addRecipe` and `AddRecipe` all work the same.

<br>

---
### Comments

Comments can be used to make scripts easier to understand. They will not be loaded by **Tweaked** and are for informational purposed only.

Comments have the syntax `#<comment>` or `//<comment>`, e.g :

```python
# this will be completely ignored
```

<br>

---
### Logging

You can print a message to the log file by using the print option, this can help with debugging your scripts, e.g :

```python
# will print Hello log file to tweaked.log
print("Hello log file");
```

<br>

---
### ModOnly Option

You may wish for a script to only run if a specific mod is loaded.

This can be done by specifying a modonly option, this will prevent any actions below it being loaded if the specified mod isn't also loaded.

```python
# will prevent anything after this line being loaded if jei isn't found
@modonly(jei)
```

<br>

---
## Your First Script

Create a new file named `test.tweak` inside the `/Tweaked/Scripts` directory

For this example we will print a message to the log file. `print` is a special action that we can use to do this.

Inside `test.tweak` paste the following code :  
```
print("Test Message");
```

Now run minecraft and once it's loaded look inside the `tweaked.log` file. You should see that your script has output the specified message.