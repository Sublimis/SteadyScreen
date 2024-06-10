# ⛵ [SteadyScreen](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen) service for Android and Wear 🏝️

### Make on-screen reading easier by softening small movements of mobile screens.


Ever been in a moving vehicle trying to read?


- This is a service that allows compatible Android and Wear apps to easily soften small device movements within their user interface.
- It can improve screen readability and possibly alleviate motion sickness while on the go, e.g. while reading in a moving vehicle or walking.


## List of apps supporting SteadyScreen service

(as of 2024-05)

- [Wikipedia (developer build)](https://github.com/Sublimis/SteadyScreen/tree/main/wikipedia-android): We compiled this from [the original source](https://github.com/Sublimis/apps-android-wikipedia) on 2024-03-22. You are welcome to compile your own APK.

- [Urban Biker](https://urban-bike-computer.com/): Supports the service on the main and overview screens, and also has its own screen stabilization implementation.

*Let us know if you've made an app that should be included in the list!*

## How to make your application compatible

- The easiest way is to use the [SteadyViews](https://github.com/Sublimis/SteadyViews) library, which contains ready-to-use "Steady…" implementations of most common Android layouts (like e.g. LinearLayout or ConstraintLayout).
- Use the [SteadyView](https://github.com/Sublimis/SteadyView) library if you have a custom View or ViewGroup that you want to make compatible.


## What happens if the service is not installed

Absolutely nothing. Your Views and ViewGroups continue to function as if the SteadyScreen service never existed, and we all get on with our merry lives.


## Enable or disable programatically

Call the `ISteadyView.setSteadyViewEnabled(final boolean enabled)` method on your ISteadyView to disable or (re)enable the functionality.

Disable:
```java
myView.setSteadyViewEnabled(false);
```

Enable:
```java
myView.setSteadyViewEnabled(true);
```

Note, this does not disable/enable the service, it just tells the View to ignore all service inputs.
Call the `boolean ISteadyView.isSteadyViewEnabled()` on your ISteadyView to check the enabled state.


## About the service

[SteadyScreen service](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen) application uses the [AccessibilityService API](https://developer.android.com/reference/android/accessibilityservice/AccessibilityService) to retrieve interactive windows on the screen, in order to find compatible ones. It then sends multiple "move window" accessibility actions to such windows, as needed, to perform the intended function. The service never collects, stores nor shares any data that can be of personal and confidential nature in any way.

⚡ The service has been crafted very meticulously, in order to minimize resource usage and maximize performance. It uses only the accelerometer sensor to achieve the goal.


##  :mortar_board: Translations

#### Contribute

[https://translate.urban-bike-computer.com/engage/stilly/](https://translate.urban-bike-computer.com/engage/stilly/)


#### Why translate?

To see the app in your native language, and to support the project!

Also, translators are rewarded with free app licenses. Please [contact us via email](mailto:contact@urban-bike-computer.com?subject=Stilly_translation_license_request) to obtain your license!


#### More info

[https://urban-bike-computer.com/translate/](https://urban-bike-computer.com/translate/)



## History

The technology behind the SteadyScreen first appeared in our [Urban Biker](https://urban-bike-computer.com/) app in late 2022. It took us a while to realize it was cool enough to release it as a separate semi-open source project.


## Project components

- [SteadyScreen service app](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen): The engine behind the scenes.
- [SteadyViews library](https://github.com/Sublimis/SteadyViews): Ready-to-use "Steady…" implementations of most common Android layouts (like e.g. LinearLayout or ConstraintLayout).
- [SteadyView library](https://github.com/Sublimis/SteadyView): Core classes and methods. To be used for custom View or ViewGroup implementations.
- [SteadyService library](https://github.com/Sublimis/SteadyService): Details of the service implementation.
