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
* Hot Reload, which enables productive development
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

**Does Flutter use my system’s OEM widgets?**

No. Instead, Flutter provides a set of widgets (including Material Design and Cupertino (iOS-styled) widgets), managed and rendered by Flutter’s framework and engine

If Flutter reused the OEM widgets, the quality and performance of Flutter apps would be limited by the quality of those widgets.

Modern app design trends point towards designers and users wanting more motion-rich UIs and brand-first designs. In order to achieve that level of customized, beautiful design, Flutter is architectured to drive pixels instead of the OEM widgets.

**What language is Flutter written in?**

Dart for the framework and widgets. The underlying graphics framework and the Dart virtual machine are implemented in C/C++.

**Why did Flutter choose to use Dart?**

Dart runtimes and compilers support the combination of two critical features for Flutter: a JIT-based fast development cycle that allows for shape changing and stateful hot reloads in a language with types, plus an Ahead-of-Time compiler that emits efficient ARM code for fast startup and predictable performance of production deployments.

**What kind of app performance can I expect?**

Flutter apps run via natively compiled code—no interpreters are involved. This means Flutter apps start quickly(to help developers easily achieve a constant 60fps).

**What devices and OS versions does Flutter run on?**
- Mobile operating systems: Android Jelly Bean, v16, 4.1.x or newer, and iOS 8 or newer.
- Mobile hardware: iOS devices (iPhone 4S or newer) and ARM Android devices.
- Flutter supports building ahead-of-time (AOT) compiled libraries for x86_64, armeabi-v7a, and arm64-v8a.
- Apps built for ARMv7 or ARM64 run fine (using ARM emulation) on many x86 Android devices.
- We support developing Flutter apps with Android and iOS devices, as well as with Android emulators and the iOS simulator.
- We test on a variety of low-end to high-end phones and tablets, but we don’t yet have an official device compatibility guarantee.

**Can I use Flutter inside of my existing native app?**

Yes, one fullscreen Flutter instance can be integrated per app on Android and iOS. [See the integration documentation](https://flutter.dev/docs/development/add-to-app)

**Can I access platform services and APIs like sensors and local storage?**

- Flutter gives developers out-of-the-box access to some platform-specific services and APIs from the operating system (but flutter don’t intend to build cross-platform APIs for all native services and APIs.)
- A number of platform services and APIs have ready-made packages available on pub.dev.
- You can use Flutter’s asynchronous message passing system to create your own integrations with platform and third-party APIs.[See How?](https://flutter.dev/docs/development/platform-integration/platform-channels#pigeon)

**Can I interop/run/use with my mobile platform’s default programming language?**

Flutter supports calling into the platform, including integrating with Java or Kotlin code on Android, and ObjectiveC or Swift code on iOS. This is enabled via a flexible message passing style where a Flutter app might send and receive messages to the mobile platform using a `BasicMessageChannel`. [See example](https://github.com/flutter/flutter/tree/master/examples/platform_channel)

**How do I write parallel and/or concurrent apps for Flutter?**

Flutter supports isolates. Isolates are separate heaps in Flutter’s VM, and they are able to run in parallel (usually implemented as separate threads). 
[example](https://github.com/flutter/flutter/blob/master/examples/layers/services/isolate.dart)

**Can I run Dart code in the background of an Flutter app?**

Yes[example](https://medium.com/flutter/executing-dart-in-the-background-with-flutter-plugins-and-geofencing-2b3e40a1a124)

**My app has a Debug banner/ribbon in the upper right. Why am I seeing that?**

The debug configuration runs your Dart code in a VM (Virtual Machine) enabling a fast development cycle with hot reload

The debug configuration also checks all asserts, which helps you catch errors early during development, but imposes a runtime cost. The “Debug” banner indicates that these checks are enabled.

**Programming paradigm used by Flutter’s framework**

- **Composition** Widgets are themselves often composed of many small, single-purpose widgets that combine to produce powerful effects.

Most widgets in the Flutter widget library are built in this way. For example, the Material `FlatButton` class is built using a `MaterialButton` class, which itself is built using an `IconTheme`, an `InkWell`, a `Padding`, a `Center`, a `Material`, an `AnimatedDefaultTextStyle`, and a `ConstrainedBox`. The `InkWell` is built using a `GestureDetector`. The `Material` is built using an `AnimatedDefaultTextStyle`, a `NotificationListener`, and an `AnimatedPhysicalModel`. And so on. It’s widgets all the way down.

https://flutter.dev/docs/resources/faq#what-programming-paradigm-does-flutters-framework-use

https://flutter.dev/docs/development/data-and-backend/state-mgmt/declarative

https://flutter.dev/docs/get-started/flutter-for/declarative
