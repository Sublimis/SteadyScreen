# ⛵ [Stilly](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen) screen stabilizer service for Android and Wear 🏝️

### Make on-screen reading easier by softening small movements of mobile screens.


Ever been in a moving vehicle trying to read?


- This is a service that allows compatible Android and Wear apps to easily soften small device movements within their user interface.
- It can improve screen readability and possibly alleviate motion sickness while on the go, e.g. while reading in a moving vehicle or walking.


## List of apps supporting Stilly service

(as of 2024-03)

- [Wikipedia (developer build)](https://github.com/Sublimis/SteadyScreen/tree/main/wikipedia-android): We compiled this from [the original source](https://github.com/Sublimis/apps-android-wikipedia) on 2024-03-22. You are welcome to compile your own APK.

- [Urban Biker](https://urban-bike-computer.com/): Supports the service on the main and overview screens, and also has its own screen stabilization implementation.

*Let us know if you've made an app that should be included in the list!*

## How to make your application compatible

- The easiest way is to use the [SteadyViews](https://github.com/Sublimis/SteadyViews) library, which contains ready-to-use "Steady…" implementations of most common Android layouts (like e.g. LinearLayout or ConstraintLayout).
- Use the [SteadyView](https://github.com/Sublimis/SteadyView) library if you have a custom View or ViewGroup that you want to make compatible.
- Use the [SteadyService](https://github.com/Sublimis/SteadyService) library if you want to implement your own screen stabilizer service that won't need [Stilly](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen) to be installed.


## What happens if the service is not installed

Absolutely nothing. Your Views and ViewGroups continue to function as if the Stilly screen stabilizer service never existed, and we all get on with our merry lives.


## Enable or disable programatically

Call the `ISteadyView.setSteadyViewEnabled(final boolean enabled)` method on your ISteadyView to disable or (re)enable the functionality:

```
MyCustomView extends View implements ISteadyView
{
   ...
}

MyCustomView myCustomView = new MyCustomView();

...

myCustomView.setSteadyViewEnabled(false);

...

myCustomView.setSteadyViewEnabled(true);
```

Note, this does not disable/enable the service, it just tells the View to ignore all service inputs.
Call the `boolean ISteadyView.isSteadyViewEnabled()` on your ISteadyView to check the enabled state.


## About the service

[Stilly](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen) application uses the [AccessibilityService API](https://developer.android.com/reference/android/accessibilityservice/AccessibilityService) to retrieve interactive windows on the screen, in order to find compatible ones. The service then sends multiple "move window" accessibility actions to such windows, as needed, to perform the intended function. The data accessed during the process, using Android's AccessibilityService API, can be of personal and confidential nature (i.e. sensitive information). The application never collects, stores nor shares that data in any way.

⚡ The service has been crafted very meticulously, in order to minimize resource usage and maximize performance. It uses only the accelerometer sensor to achieve the goal.


## History

The technology behind the Stilly first appeared in our [Urban Biker](https://urban-bike-computer.com/) app in late 2022. It took us a while to realize it was cool enough to release it as a separate semi-open source project.


## Project components

- [Stilly app](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen): The engine behind the scenes.
- [SteadyService library](https://github.com/Sublimis/SteadyService): If you want to implement your own screen stabilizer service that won't need Stilly.
- [SteadyViews library](https://github.com/Sublimis/SteadyViews): Ready-to-use "Steady…" implementations of most common Android layouts (like e.g. LinearLayout or ConstraintLayout).
- [SteadyView library](https://github.com/Sublimis/SteadyView): Core classes and methods. To be used for custom View or ViewGroup implementations.
