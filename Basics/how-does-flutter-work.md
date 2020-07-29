# Flutter - How does it work behind the scenes?

The Flutter refers to two major concepts
1. **Flutter SDK**: is a collection of tools that allows you to build any kind of app for both Android & iOS platform in one codebase.
2. **Flutter Framework**: Basically it provides all the predefined widgets/widget library, utility functions & packages.

Flutter uses Dart as a programming language & apps build/developed by flutter can be run on Android & iOS. so that, we need to compile dart code to native machine android/ios code.
> This compilation task is done by Flutter SDK.

Flutter doesn't use any kind of web view (like cordova) or native controls of the operating system (via bridging like React Native). Instead flutter uses it's own high performance **rendering engine(Skia)**, to draw widgets. (it draws the UI from scratch, not acts as a wrapper on top of native UI components like other frameworks do.)

There are two kinds of compilation
* Static Compilation: Statically compiled programs are all translated into machine code before execution. Ex: AOT(Ahead of Time) - C/C++.
* Dynamic Interpretation: is executed by one-to-one translation. Ex: JIT(Just in Time) - Javascript/Python.

> The DART runtime and compiler also support a combination of two key features - JIT & AOT.

The Dart source code is compiled to native code using Dart's AoT compilation feature. It still needs parts of the the Dart VM (some runtime components like garbage collection) to run though, but the code is compiled to native code ahead of time.

# Why to Use Flutter for Building Cross-Platform Apps?
Flutter is an open-source, cross-platform toolkit used for building apps for mobile OS, web, and desktop with the same code base

But Flutter isn’t the only cross-platform framework. Xamarin, React Native, Cordova – they also let developers write the code once and use it on several platforms.
**What can Flutter do?*** It combines the quality of native apps with the flexibility of cross-platform development. Flutter renders the same look as a native app: it draws the UI from scratch, not acts as a wrapper on top of native UI components like other frameworks do.

### What is Flutter programming language?
Dart is an open-source and object-oriented programming language also created by Google.

Along with Dart, there’s high-speed C++ in Flutter’s core(behind the scene). The resulting app produces such high fps ( 60 or 120 fps animations) it feels like a native one.

Dart uses Skia C++ graphics engine, so it does not require any bridge that slows down the app like with React Native. Flutter does not use native components in any form, so developers don't have to make bridges for communicating with them. Instead, similar to game engines like Unity or Unreal (and games have a very dynamic UI), Flutter draws the interface on its own.

### Benefits of Flutter App Development
1. Flutter apps are budget-friendly
2. Native-like performance
3. Development goes faster
4. Hot Reload feature (JIT complier)

### Flutter Disadvantages
1. Relatively small proven expertise
2. Limited number of third-party libraries
3. Large file size - there’s plenty of [documentation](https://flutter.dev/docs/perf/app-size) on reducing the app’s size.

Also refer: https://www.youtube.com/watch?v=l-YO9CmaSUM
