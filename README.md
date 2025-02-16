# light_dark_mode

A very minimal and simple all that has a button to swich between dark theme and light theme using a created ThemeProvider and the provider package.

## How does it work

in the `lib` folder there are 3 other folders - 
- components
- pages
- theme

The ***components*** folder contains 
- box.dart - a StateLessWidget called `MyBox` that returns a Container which has it's color set via a `color` parameter being passed into it along with any `child` widgets, both parameters are required
- button.dart - a StateLessWidget called `MyButton` that returns a GestuerDetector which has it's onTap function passed via a parameter called `onTap`, the child is a Container which has it's color set via a `color` parameter.

The ***pages*** folder contains the `home_page.dart` - 
this is a StatelessWidget called `HomePage` which returns a Scaffold widget, that has the backgroundColor set as per the ThemeData via the theme_provider. 
The body contains the `MyBox` component/custom widget which has the color set via the ThemeData via the theme_provider, and the child is the `MyButton` component/custom widget which has the color set via the ThemeData via the theme_provider and the onTap functionality via the 'toggleTheme()' method via the theme_provider.

The ***theme*** folder contains - 
- theme_provider.dart - is a class called ThemeProvider with the ChangeNotifier subclass. This sets a ThemeData private variable called `_themeData` to lightMode as default. Another vairable called themeData is created for getting the current _themeData, and we set this other variable to what ever the current _themeData is, and we notifyListeners().
  There is also a method called `toggleTheme()` which checks to see if the current _themeData is lightMode, and if so we set themeData to darkMode, else we set themeData to ligheMode
- theme.dart - This file contains the surface(was background), primary and secondary colorScheme for lightMode and darkMode.

The `main.dart` file contains the ChangeNotifierProvider that creates the ThemeProvider and returns `MyApp` which consists of the `HomePage` widget and provides the theme to the whole app.

Light Mode - 

![image](https://github.com/user-attachments/assets/42a96add-eda7-41ab-9fe9-dc3864b7c7ce)

Dark Mode - 

![image](https://github.com/user-attachments/assets/72fdcacc-3381-481d-bab7-9f3c6e1d1ecf)


