# ANSWERS.md

## 1. GitHub Repository Link

GitHub Repository: `https://github.com/renzestopito-del/flutter_basics_lab.git`

## 2. Last Three `build()` Called Lines from Activity 2

```text
build() called: 4 glasses
build() called: 5 glasses
build() called: 6 glasses
```

## 3. Experiment Observations

### Activity 2: Changing `_glasses` Outside `setState()`

When I changed `_glasses` outside `setState()`, the number of glasses and progress bar did not update immediately on the screen. This happened because Flutter was not notified that the state had changed. When I placed the change back inside `setState()`, the UI updated correctly.

### Activity 3: Removing `Expanded` from a `StatBox`

When I removed `Expanded` from a `StatBox`, the layout changed because the box no longer shared the available space equally with the other boxes. When I added `Expanded` back, the boxes shared the available space more evenly and the layout returned to normal.

### Activity 5: Changing the Button Corner Radius

When I changed the button corner radius from `8` to `20` in `buildTheme()`, the Elevated button became more rounded and gave the app a softer appearance. The button's padding remained the same, but its corners became more curved.

## 4. Review Questions

### 1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each from this lab.

A `StatelessWidget` does not manage changing state inside itself. An example is `ProfileCard` in Activity 1. A `StatefulWidget` can manage changing data and update the UI when its state changes. An example is `ThemeDemoApp` in Activity 5.

### 2. Why is a StatefulWidget written as two classes? What does each class do?

A `StatefulWidget` uses two classes because they have different responsibilities. The first class defines the widget, while the second class extends `State` and contains the changing data and the `build()` method. The State class updates the UI when `setState()` is called.

### 3. In Activity 2, what happened when you changed `_glasses` outside `setState()`? Why?

When I changed `_glasses` outside `setState()`, the number and progress bar did not update immediately. This happened because Flutter was not notified that the state had changed. Using `setState()` tells Flutter to rebuild the UI.

### 4. Looking at the Debug Console in Activity 2, when is `build()` called?

The `build()` method is called when Flutter needs to create or update the UI. In Activity 2, it was called when the screen first appeared and when I tapped the button that changed the number of glasses inside `setState()`.

### 5. Explain the main axis and the cross axis of a Row and of a Column.

In a `Row`, the main axis is horizontal and the cross axis is vertical. In a `Column`, the main axis is vertical and the cross axis is horizontal. These axes determine how widgets are arranged and aligned.

### 6. In Activity 3, what happened when you removed Expanded from a StatBox? What does Expanded do?

When I removed `Expanded` from a `StatBox`, the layout changed because the box no longer shared the available space equally with the other boxes. `Expanded` allows a widget to fill the available space along the main axis of its parent `Row` or `Column`.

### 7. Why do we use GridView.builder for the menu instead of a Column with many children?

We use `GridView.builder` because it arranges menu items in rows and columns and supports scrolling. It also builds items as needed, making it useful for displaying many menu items efficiently. A `Column` arranges items vertically and is less suitable for a large, scrollable grid.

### 8. How do Stack and Positioned create the Best seller badge in Activity 4?

`Stack` places widgets on top of each other. `Positioned` places the Best seller badge at a specific location, such as the top-left corner of a menu card. This allows the badge to appear over the menu item.

### 9. What is the difference between customizing with ThemeData and with a style on one widget? Give one example of each from Activity 5.

`ThemeData` customizes the appearance of components throughout the app. For example, `elevatedButtonTheme` sets the shape and padding of Elevated buttons. A style applied directly to one widget customizes only that widget, such as setting a specific background color on a single button.

### 10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the change reach MaterialApp?

The `_ThemeDemoAppState` class holds the `_isDark` state. When I flip the switch, `SettingsPage` calls the `onDarkChanged` callback. The `_setDark()` method updates `_isDark` inside `setState()`, causing `MaterialApp` to rebuild and select the light or dark theme through `themeMode`.
