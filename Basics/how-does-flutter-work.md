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

