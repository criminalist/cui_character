# CleanUI (cui) character
An advanced character and clothes editor for esx framework that aims to be comfortable to use, hide complexity and blend in with original GTA V interface elements.

## Character Customization Features
I tried to cover every feature that GTA Online character creator offers, notably:

* Heritage (parent face and skin color blending) working exactly like the one made by Rockstar
* Property names displayed whenever possible instead of raw numbers

I have made improvements in places where I thought Rockstar's creator didn't do a particularly good job:

* Properties are grouped in a more intuitive way
* "2D grids" have been replaced with sliders
* Percentage values are clearly displayed

## Additional features

* Flexible camera that can be zoomed and rotated with mouse as well as switched between `face`, `body` and `legs` views
* Native, in-game sound effects
* Optional (configurable) map locations where characters can be customzied after creation (barber shops, hospital plastic surgery units, clothes shops)
* Optional esx_identity integration (disabled by default, check instructions in config.lua to enable)

## Requirements and usage notes
**I intended this to be fully functional resource with minimal configuration. Editing and saving characters to the database *should* work out-of-the-box.**

In order to use this resource, legacy version of [es_extended](https://github.com/esx-framework/es_extended/tree/v1-final) is required. In addition, the `skin data column` that esx_skin uses is required (SQL file included).

It will most likely conflict with esx_skin as it labels and uses some data in exact same way.

Optional integration with [esx_identity](https://github.com/esx-framework/esx_identity) is possible.
Optional features can be configured editing `config.lua` file.

Admins can use `/identity`, `/features`, `/style`, `/apparel` commands to open respective tabs or `/character` to open full character customization anywhere.

## Known Issues

### Clothes selection
Clothes customization is sort-of experimental. It relies on pulling entire data set from the game using natives and filtering them to only those that Rockstar gave names. This seems to result in a more limited selection as well as a noticable loading time when building the html dynamically.

I would be grateful if someone could point out a way to do it better. Preferably one that does not involve including and parsing custom, several megabytes large data files.

Gloves have been omitted entirely from the clothes selection, they are really messy and I have not found a way to automatically match them with other currently selected components. It would require an arduous, manual approach to get them in now.