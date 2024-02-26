# ⛵ [Stilly](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen) screen stabilizer service for Android and Wear 🏝️

### Make on-screen reading easier by softening small movements of mobile screens.


Ever been in a moving vehicle trying to read?


- This is a service that allows compatible Android and Wear apps to easily soften small device movements within their user interface.
- It can improve screen readability and possibly alleviate motion sickness while on the go, e.g. while reading in a moving vehicle or walking.


## How to make your application compatible

- The easiest way is to use the [SteadyViews](https://github.com/Sublimis/SteadyViews) library, which contains ready-to-use "Steady…" implementations of most common Android layouts (like e.g. LinearLayout or ConstraintLayout).
- Use the [SteadyView](https://github.com/Sublimis/SteadyView) library if you have a custom View or ViewGroup that you want to make compatible.


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


## List of apps supporting Stilly service

(as of 2024-02-26)

- [UrbanBiker](https://urban-bike-computer.com/): Supports the service on the main and overview screens while the tracking is off; While the tracking is on, the app has it's own steady implementation.



More soon...
