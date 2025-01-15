# ⛵ [SteadyScreen](https://play.google.com/store/apps/details?id=com.sublimis.steadyscreen) service for Android and Wear 🏝️

### Improve screen readability of a handheld device while walking or traveling

Make reading on the go more enjoyable!


- This service allows compatible Android and Wear applications to easily counteract small device movements within their user interface.
- This improves screen readability of a handheld device while walking or traveling.


## How to make your application compatible

- Use the [SteadyScreenLib](https://github.com/Sublimis/SteadyScreenLib) library.


## What happens if the service is not installed

Absolutely nothing. Your Views and ViewGroups continue to function as if the SteadyScreen service never existed. They will never get a callback from the service, so nothing happens.


## List of apps supporting SteadyScreen service

(as of 2025-01)

- [Wikipedia](https://github.com/Sublimis/wikipedia-steady): Forked
  from [the original source code](https://github.com/Sublimis/apps-android-wikipedia). You are welcome to compile your own APK from this.
- [Next Player](https://github.com/Sublimis/nextplayer-steady): Forked
  from [the original source code](https://github.com/anilbeesetti/nextplayer). You are welcome to compile your own APK from this.
- [Urban Biker](https://urban-bike-computer.com/): Supports the service on the main and overview screens, and also has its own screen stabilization
  implementation.

*Let us know if you've made an app that should be included in the list!*


## About the service

⚡ The service has been crafted very meticulously, in order to minimize resource usage and maximize performance.


##  :mortar_board: Translations

#### Contribute

[https://translate.urban-bike-computer.com/projects/steadyscreen/](https://translate.urban-bike-computer.com/projects/steadyscreen/)


#### Why translate?

To see the app in your native language, and to support the project!

Also, translators are rewarded with free app licenses. Please [contact us via email](mailto:contact@urban-bike-computer.com?subject=SteadyScreen_translation_license_request) to obtain your license!


#### More info

[https://urban-bike-computer.com/translate/](https://urban-bike-computer.com/translate/)


## History

The technology behind the SteadyScreen first appeared in our [Urban Biker](https://urban-bike-computer.com/) app in late 2022. It took us a while to
realize it was cool enough to release it as a separate semi-open source project.
