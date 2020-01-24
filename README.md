GodotAdcolony - Intersistial
=====
This is an Android Adcolony-Intersistial plugin for Godot Engine (https://github.com/okamstudio/godot) 3.2 or higher.

How to use
----------
- Configure, install  and enable the "Android Custom Template" for your project, just follow the [official documentation](https://docs.godotengine.org/en/latest/getting_started/workflow/export/android_custom_build.html);
- download or clone this repository;
- drop the ```GodotAdcolonyIntersistial``` directory (from this repository) inside the ```res://android/``` directory on your Godot project.
- on the Project Settings -> Android -> Modules, add the string:

```
org/godotengine/godot/GodotAdColonyIntersistial
```

API Reference
-------------
The following methods are available:
```python

# Show Toast
# @param String message
# @param bool max (if true = LONG, else SHORT)
showToast(message, max)

```
Sample example
-------------
## Example:
```python

var Toast
onready var editText = get_node("TextEdit")

func _ready():
	if(Engine.has_singleton("ZubcovToast")):
		Toast = Engine.get_singleton("ZubcovToast")
		pass
	get_node("btn_show").connect("pressed", self, "showToast")
	pass


#events

func showToast():
	Toast.showToast(editText.text, true)
	print(editText.text)
	pass

```

------------


--------------

```
adb logcat -s godot
```

References
-------------
Based on the works of:
* https://github.com/kloder-games/godot-adcolony

License
-------------
MIT license