# Introduction of Flutter

**What is Flutter?**

Flutter is Google’s portable UI toolkit for crafting beautiful, natively compiled applications for mobile, web, and desktop from a single codebase.

**What kinds of apps can I build with Flutter?**

Flutter is optimized for 2D mobile apps that want to run on both Android and iOS. Flutter is also great for interactive apps that you want to run on your web pages or on the desktop.

You can build full-featured apps with Flutter, including camera, geolocation, network, storage, 3rd-party SDKs, and more.

**Who makes Flutter?**

Flutter is an open source project, with contributions from Google and the community.

**What makes Flutter unique?**

Flutter is different than most other options for building mobile apps because Flutter uses neither WebView nor the OEM widgets that shipped with the device. Instead, Flutter uses its own high-performance rendering engine to draw widgets.

**What does Flutter provide?**
* Heavily optimized, mobile-first 2D rendering engine with excellent support for text
* Modern react-style framework
* Rich set of widgets implementing Material Design and iOS-style.
* APIs for unit and integration tests
* Interop and plugin APIs to connect to the system and 3rd-party SDKs
* Dart DevTools for testing, debugging, and profiling your app
* Hot Reload
* Command-line tools for creating, building, testing, and compiling your apps

**Does Flutter come with a framework?**

Yes! Flutter ships with a modern framework, inspired by React. Flutter’s framework is designed to be layered and customizable (and optional). Developers can choose to use only parts of the framework, or a different framework.

**Layers of flutter framework**

The Flutter framework is organized into a series of layers, with each layer building upon the previous layer in terms of complexity and clearly arranged in layers of decreasing complexity. 

The top most layer is widget specific to Android and iOS. The next layer has all flutter native widgets. The next layer is Rendering layer, which is low level renderer component and renders everything in the flutter app. Layers goes down to core platform specific code

The general overview of a layer in Flutter is specified in the below diagram −

![image]()
![image]()

[See Examples of Flutter's layered architecture](https://github.com/flutter/flutter/tree/master/examples/layers)

**What technology is Flutter built with?**

Flutter is built with C, C++, Dart, and Skia (a 2D rendering engine).

**How does Flutter run my code on Android?**
1. The engine’s C and C++ code are compiled with Android’s NDK. The Dart code (both the SDK’s and yours) are ahead-of-time (AOT) compiled into native, ARM, and x86 libraries. 
2. Those libraries are included in a “runner” Android project, and the whole thing is built into an APK. 
3. When launched, the app loads the Flutter library. Any rendering, input, or event handling, and so on, is delegated to the compiled Flutter and app code. This is similar to the way many game engines work.
4. Debug mode builds use a virtual machine (VM) to run Dart code (hence the “debug” banner they show to remind people that they’re slightly slower) in order to enable Stateful Hot Reload.

**How does Flutter run my code on iOS?**

1. The engine’s C and C++ code are compiled with LLVM. The Dart code (both the SDK’s and yours) are ahead-of-time (AOT) compiled into a native, ARM library. 
2. That library is included in a “runner” iOS project, and the whole thing is built into an .ipa.
3. When launched, the app loads the Flutter library. Any rendering, input or event handling, and so on, are delegated to the compiled Flutter and app code. This is similar to the way many game engines work.
4. Debug mode builds use a virtual machine (VM) to run Dart code (hence the “debug” banner they show to remind people that they’re slightly slower) in order to enable Stateful Hot Reload.

