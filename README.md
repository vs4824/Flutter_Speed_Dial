# Flutter Speed Dial

Flutter package to render a Material Design Speed Dial.

## Usage

The SpeedDial widget is built to be placed in the Scaffold.floatingActionButton argument, replacing the FloatingActionButton widget. You can set its position using Scaffold.floatingActionButtonLocation argument. It can also be used with Scaffold.bottomNavigationBar and Snackbar.

Null safety is available from version 3.0.5 ( It is also backward compatible, meaning you can use it with non null safe code too )

## Labels

SpeedDial can take any Widget as label SpeedDial will use Extended FloatingActionButton property if label is specified. It also have activeLabel property by which you can specify the label which is shown when SpeedDial is open. It also comes with its labelTransitionBuilder which defaults to fade transition.

Also Every child's button have label property which accepts String which can be styled by using labelStyle. If you want to specify a widget then you can use labelWidget.
If the label parameter is not provided, then the label will be not rendered.

### Types of child for SpeedDial (Ordered by their priority)

####  Animated Icon using animatedIcon property

SpeedDial's AnimatedIcon has two specific parameters:

1. animatedIcon takes an AnimatedIconData widget

2. animatedIconTheme takes IconThemeData

####  Widget using child & activeChild property

SpeedDial's Widget has two specific parameters:

1. child takes a widget and is the default placeholder if dial is not open.

2. activeChild takes a widget and is the child's Widget which is used when dial is open, not required.

####  IconData using icon & activeIcon property

SpeedDial's IconData has three specific parameters:

1. icon takes a IconData and is the default placeholder if dial is not open.

2. activeIcon takes a IconData and is the child's IconData which is used when dial is open, not required.

3. iconTheme takes its IconThemeData which includes color and size.

## Handle spacing

There are various properties for SpeedDial by which you can adjust the spacing:

1. spacing - This parameter handles the space b/w speed dial and its children.

2. spaceBetweenChildren - As the name suggests, this is used to adjust the space b/w every child element

3. childPadding - This will adjust the padding of children speed dial button, this will help you to control the size of the children button more effectively.

4. childMargin - This will help you to adjust the margin b/w children speed dial button and its label.

## Close on WillPop

Closes automatically on back button press, if dial is open. If you don't want this behaviour then simply change the value of closeDialOnPop to false.

### How to use openCloseDial property:

1. Create a value notifier named isDialOpen:

   ```
   ValueNotifier<bool> isDialOpen = ValueNotifier(false);
   ```
   
2. Then set openCloseDial to isDialOpen in your SpeedDial:

   ```
   SpeedDial(
   ...
   openCloseDial: isDialOpen,
   ...
   )
   ```
   
3. Now you can change the state of dial open:

   ```
   isDialOpen.value = false;
   ```