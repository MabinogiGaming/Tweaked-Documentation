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

The syntax for a command is `/tweaked command arguments`.

!!! example
	```python
	# This command will print registry information on the currently held item
	/tweaked hand
	```

!!! note
	/tweaked can be shortened to /tw, e.g : `/tw hand`

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

The full syntax for an action is : `tweak.<action>(<arguments);`.

!!! example
	```python
	# This action will remove the recipe specific by "recipeName"
	tweak.recipes.remove("recipeName");
	```
	
<br>

`Variables` can be used to store `Arguments`, allowing them to be used in `Methods`.

`Variables` have the syntax `$<variable name> = <variable type>(<arguments>);

!!! example
	```python
	# This does exactly the same as the previous example, except using a variable.
	$testVar = String("recipeName");
	tweak.recipes.remove($testVar);
	```

!!! note
	tweak can be ignored in order to make scripts shorter, e.g : `.recipes.remove("recipeName");` is valid.
	
!!! note
	Actions and Variables are case insensitive, `addrecipe`, `addRecipe` and `AddRecipe` all work the same.

<br>

---
### Comments

Comments can be used to make scripts easier to understand. They will not be loaded by **Tweaked** and are for informational purposed only.

Comments have the syntax `#<comment>` or `//<comment>`.

!!! example
	```python
	# this will be completely ignored
	```

<br>

---
### Logging

You can print a message to the log file by using the print option, this can help with debugging your scripts.

!!! example
	```python
	# will print Hello log file to tweaked.log
	print("Hello log file");
	```

<br>

---
### ModOnly Option

You may wish for a script to only run if a specific mod is loaded.

This can be done by specifying a modonly option, this will prevent any actions below it being loaded if the specified mod isn't also loaded.

!!! example
	```python
	# will prevent anything after this line being loaded if jei isn't found
	@modonly(jei)
	```