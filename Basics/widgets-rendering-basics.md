# How Flutter Renders Widgets?
> “Everything is a widget in Flutter”

Let’s see what the flutter document has to say about Widget in its official documentation .
> A widget is an **immutable** description of part of a User Interface.

how can User Interface be Immutable (unchangeable) as we all know that UIs are not at all immutable 
as we readily mutate different parts of our UIs by swapping pieces in|out by adding divergent widgets. 
So, If Widgets are Immutable then

#### So,How Does Flutter Manage State of your UI?, How represents change?
It actually manages this through with the help of 3 trees instead of a Singleton for the State Management.

> Flutter has three trees
* Widget Tree (Configure) -> Widget describes the configuration **for an element**.
* Element Tree (Lifecycle) -> Element: an instantiation of a widget at a perticular location in the tree. Element is mutable tree and it is managing life cycle of widets.
* RenderObject Tree (Paint) -> RenderObject: handles size, layout and painiting UI. When flutter draws ui, it doesn't look at tree of widgets. It looks at a tree of RenderObject.

**Flutter manage these 3 Different tree in for its rendering process:**

![alt three tree](./three-tree.png)

So as already seen that a widget is immutable, and so that kind of makes sense because you are working with a **declarative framework** so you grasp what your UI is going to look like & configure it with widgets.
https://flutter.dev/docs/get-started/flutter-for/declarative

Widget describes configuration of an element, Elements are particularly an instantiation of those widgets. Elements manage updating and changing of the UI, controlling lifecycle of widgets. Lastly, we have a RenderObject which is what’s going to lay out and paint your UI.

**Why are flutter using 3 trees?**
For this lets look at source code from flutter framework for when it create a flutter app.

Flutter app calls runApp() function initially:

