GodotAdcolony - Intersistial
=====
This is an Android Adcolony-Intersistial plugin for Godot Engine (https://github.com/okamstudio/godot) 3.2 or higher.

How to use
----------
- Configure, install  and enable the "Android Custom Template" for your project, just follow the [official documentation](https://docs.godotengine.org/en/latest/getting_started/workflow/export/android_custom_build.html);
- download or clone this repository;
- drop the ```GodotAdcolonyIntersistial``` directory (from this repository) inside the ```res://android/``` directory on your Godot project.
- on the Project Settings -> Android -> Modules, add the string:

In project goto Export > Target > Android:

	Options:
		Permissions on:
			- Access Network State
            - Access Fine Location (Recommended)
			- Internet

```
org/godotengine/godot/GodotAdColonyIntersistial
```


API Reference
-------------
The following methods are available:
```python

# Init AdColony
# @param string app_id AdColony APP ID
# @param string zone_id AdColony ZONE ID
# @param bool reward_confirmation_dialog Confirmation dialog before ads
# @param bool reward_result_dialog Result dialog after ads
# @param int instance_id The instance id from Godot (get_instance_ID())
init(app_id, zone_id, reward_confirmation_dialog, reward_result_dialog, instance_id)

# Callback on Ad reward (after view a rewarded ad)
_on_adcolony_reward

# Callback for Ad Request Filled (ready for show)
_on_adcolony_request_filled()

# Callback for Ad Request Not Filled (some network error for example)
_on_adcolony_request_not_filled()

# Callback for Ad Opened (on ad show)
_on_adcolony_opened()

# Callback for Ad Expiring
on_adcolony_expiring()

# Ads Methods
# --------------

# Request a new Ad
loadAd()

# Show the Ad
showAd()
```
Sample example
-------------
## Example:
```python

var adColony
var app_id = "your_app_id"
var zone_id = "your_zone_id"
var reward_confirmation_dialog: bool = true
var reward_result_dialog: bool = true

func _ready():
	if Engine.has_singleton("AdColonyIntersistial"):
		adColony = Engine.get_singleton("AdColonyIntersistial")
		adColony.init(app_id, zone_id, reward_confirmation_dialog, reward_result_dialog, get_instance_id())
		adColony.loadAd()
	pass

#events

func showAds():
	adColony.showAd()
	pass


```

------------

Can you help me?
--------------
Download my games and rate them! it helps me a lot.
Link:
* https://play.google.com/store/apps/developer?id=ZUBCOVSOFT&hl=pt-PT

From stars in my godot plugins and my adaptations for version 3.2:
Link:
* https://github.com/search?q=user%3AAlissonRichardy+Godot


--------------
```
adb logcat -s godot
```

References
-------------
Based on the works of:
* https://github.com/kloder-games/godot-adcolony
* https://github.com/AdColony/AdColony-Android-SDK



License
-------------
MIT license