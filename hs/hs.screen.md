# [docs](index.md) » hs.screen
---

Manipulate screens (i.e. monitors)

The macOS coordinate system used by Hammerspoon assumes a grid that spans all the screens (positioned as per
System Preferences->Displays->Arrangement). The origin `0,0` is at the top left corner of the *primary screen*.
(Screens to the left of the primary screen, or above it, and windows on these screens, will have negative coordinates)

## Submodules
 * [hs.screen.watcher](hs.screen.watcher.md)

## API Overview
* Variables - Configurable values
 * [strictScreenInDirection](#strictScreenInDirection)
* Functions - API calls offered directly by the extension
 * [accessibilitySettings](#accessibilitySettings)
 * [find](#find)
 * [restoreGamma](#restoreGamma)
 * [screenPositions](#screenPositions)
* Constructors - API calls which return an object, typically one that offers API methods
 * [allScreens](#allScreens)
 * [mainScreen](#mainScreen)
 * [primaryScreen](#primaryScreen)
* Methods - API calls which can only be made on an object returned by a constructor
 * [absoluteToLocal](#absoluteToLocal)
 * [availableModes](#availableModes)
 * [currentMode](#currentMode)
 * [frame](#frame)
 * [fromUnitRect](#fromUnitRect)
 * [fullFrame](#fullFrame)
 * [getBrightness](#getBrightness)
 * [getGamma](#getGamma)
 * [id](#id)
 * [localToAbsolute](#localToAbsolute)
 * [name](#name)
 * [next](#next)
 * [position](#position)
 * [previous](#previous)
 * [rotate](#rotate)
 * [screen_desktopImageURL](#screen_desktopImageURL)
 * [setBrightness](#setBrightness)
 * [setGamma](#setGamma)
 * [setMode](#setMode)
 * [setPrimary](#setPrimary)
 * [shotAsJPG](#shotAsJPG)
 * [shotAsPNG](#shotAsPNG)
 * [snapshot](#snapshot)
 * [toEast](#toEast)
 * [toNorth](#toNorth)
 * [toSouth](#toSouth)
 * [toUnitRect](#toUnitRect)
 * [toWest](#toWest)

## API Documentation

### Variables

| [strictScreenInDirection](#strictScreenInDirection)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.strictScreenInDirection`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | If set to `true`, the methods `hs.screen:toEast()`, `:toNorth()` etc. will disregard screens that lie perpendicularly to the desired axis                                                                     |

### Functions

| [accessibilitySettings](#accessibilitySettings)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.accessibilitySettings() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the current state of the screen-related accessibility settings                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing the following keys, and corresponding boolean values for whether the user has enabled these options:</li><li>  ReduceMotion (only available on macOS 10.12 or later)</li><li>  ReduceTransparency</li><li>  IncreaseContrast</li><li>  InvertColors (only available on macOS 10.12 or later)</li><li>  DifferentiateWithoutColor</li></ul>          |

| [find](#find)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.find(hint) -> hs.screen object(s)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Finds screens                                                                     |
| **Parameters**                              | <ul><li>hint - search criterion for the desired screen(s); it can be:</li><li> a number as per `hs.screen:id()`</li><li> a string pattern that matches (via `string.match`) the screen name as per `hs.screen:name()` (for convenience, the matching will be done on lowercased strings)</li><li> an hs.geometry *point* object, or constructor argument, with the *x and y position* of the screen in the current layout as per `hs.screen:position()`</li><li> an hs.geometry *size* object, or constructor argument, with the *resolution* of the screen as per `hs.screen:fullFrame()`</li><li> an hs.geometry *rect* object, or constructor argument, with an arbitrary rect in absolute coordinates; the screen</li><li>     containing the largest part of the rect will be returned</li></ul> |
| **Returns**                                 | <ul><li>one or more hs.screen objects that match the supplied search criterion, or `nil` if none found</li></ul>          |
| **Notes**                                   | <ul><li>for convenience you call call this as `hs.screen(hint)`</li></ul>                |

| [restoreGamma](#restoreGamma)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.restoreGamma()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Restore the gamma settings to defaults                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>This returns all displays to the gamma tables specified by the user's selected ColorSync display profiles</li></ul>                |

| [screenPositions](#screenPositions)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.screenPositions() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a list of all connected and enabled screens, along with their "position" relative to the primary screen                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table where each *key* is an `hs.screen` object, and the corresponding value is a table {x=X,y=Y}, where X and Y attempt to indicate each screen's position relative to the primary screen (which is at {x=0,y=0}); so e.g. a value of {x=-1,y=0} indicates a screen immediately to the left of the primary screen, and a value of {x=0,y=2} indicates a screen positioned below the primary screen, with another screen inbetween.</li></ul>          |
| **Notes**                                   | <ul><li>grid-like arrangements of same-sized screens should behave consistently; but there's no guarantee of a consistent result for more "exotic" screen arrangements</li></ul>                |

### Constructors

| [allScreens](#allScreens)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.allScreens() -> hs.screen[]`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Returns all the screens                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing one or more `hs.screen` objects</li></ul>          |

| [mainScreen](#mainScreen)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.mainScreen() -> screen`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Returns the 'main' screen, i.e. the one containing the currently focused window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.screen` object</li></ul>          |

| [primaryScreen](#primaryScreen)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen.primaryScreen() -> screen`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Gets the primary screen                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.screen` object</li></ul>          |

### Methods

| [absoluteToLocal](#absoluteToLocal)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:absoluteToLocal(geom) -> hs.geometry object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Transforms from the absolute coordinate space used by OSX/Hammerspoon to the screen's local                                                                     |
| **Parameters**                              | <ul><li>geom - an hs.geometry point or rect, or arguments to construct one</li></ul> |
| **Returns**                                 | <ul><li>an hs.geometry point or rect, transformed to the screen's local coordinate space</li></ul>          |

| [availableModes](#availableModes)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:availableModes() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table containing the screen modes supported by the screen. A screen mode is a combination of resolution, scaling factor and colour depth                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing the supported screen modes. The keys of the table take the form of "1440x900@2x" (for a HiDPI mode) or "1680x1050@1x" (for a native DPI mode). The values are tables which contain the keys:</li><li> w - A number containing the width of the screen mode in points</li><li> h - A number containing the height of the screen mode in points</li><li> scale - A number containing the scaling factor of the screen mode (typically `1` for a native mode, `2` for a HiDPI mode)</li></ul>          |
| **Notes**                                   | <ul><li>Only 32-bit colour modes are returned. If you really need to know about 16-bit modes, please file an Issue on GitHub</li><li>"points" are not necessarily the same as pixels, because they take the scale factor into account (e.g. "1440x900@2x" is a 2880x1800 screen resolution, with a scaling factor of 2, i.e. with HiDPI pixel-doubled rendering enabled), however, they are far more useful to work with than native pixel modes, when a Retina screen is involved. For non-retina screens, points and pixels are equivalent.</li></ul>                |

| [currentMode](#currentMode)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:currentMode() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table describing the current screen mode                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing the current screen mode. The keys of the table are:</li><li> w - A number containing the width of the screen mode in points</li><li> h - A number containing the height of the screen mode in points</li><li> scale - A number containing the scaling factor of the screen mode (typically `1` for a native mode, `2` for a HiDPI mode)</li><li> desc - A string containing a representation of the mode as used in `hs.screen:availableModes()` - e.g. "1920x1080@2x"</li></ul>          |

| [frame](#frame)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:frame() -> hs.geometry rect`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the screen frame, without the dock or menu.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an hs.geometry rect describing this screen's "usable" frame (i.e. without the dock and menu bar) in absolute coordinates</li></ul>          |

| [fromUnitRect](#fromUnitRect)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:fromUnitRect(unitrect) -> hs.geometry rect`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the absolute rect of a given unit rect within this screen                                                                     |
| **Parameters**                              | <ul><li>unitrect - an hs.geometry unit rect, or arguments to construct one</li></ul> |
| **Returns**                                 | <ul><li>an hs.geometry rect describing the given unit rect in absolute coordinates</li></ul>          |
| **Notes**                                   | <ul><li>this method is just a convenience wrapper for `hs.geometry.fromUnitRect(unitrect,this_screen:frame())`</li></ul>                |

| [fullFrame](#fullFrame)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:fullFrame() -> hs.geometry rect`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the screen frame, including the dock and menu.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an hs.geometry rect describing this screen's frame in absolute coordinates</li></ul>          |

| [getBrightness](#getBrightness)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:getBrightness() -> number or nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the screen's brightness                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A floating point number between 0 and 1, containing the current brightness level, or nil if the display does not support brightness queries</li></ul>          |

| [getGamma](#getGamma)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:getGamma() -> [whitepoint, blackpoint] or nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the current whitepoint and blackpoint of the screen                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing the white point and black point of the screen, or nil if an error occurred. The keys `whitepoint` and `blackpoint` each have values of a table containing the following keys, with corresponding values between 0.0 and 1.0:</li><li> red</li><li> green</li><li> blue</li></ul>          |

| [id](#id)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:id() -> number`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a screen's unique ID                                                                     |
| **Returns**                                 | <ul><li>A number containing the ID of the screen</li></ul>          |

| [localToAbsolute](#localToAbsolute)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:localToAbsolute(geom) -> hs.geometry object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Transforms from the screen's local coordinate space, where `0,0` is at the screen's top left corner,                                                                     |
| **Parameters**                              | <ul><li>geom - an hs.geometry point or rect, or arguments to construct one</li></ul> |
| **Returns**                                 | <ul><li>an hs.geometry point or rect, transformed to the absolute coordinate space</li></ul>          |

| [name](#name)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:name() -> string or nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the preferred name for the screen set by the manufacturer                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing the name of the screen, or nil if an error occurred</li></ul>          |

| [next](#next)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:next() -> screen`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the screen 'after' this one (in arbitrary order); this method wraps around to the first screen.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.screen` object</li></ul>          |

| [position](#position)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:position() -> x, y`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Return a given screen's position relative to the primary screen - see 'hs.screen.screenPositions()'                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>two integers indicating the screen position in the current screen arrangement, in the x and y axis respectively.</li></ul>          |

| [previous](#previous)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:previous() -> screen`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the screen 'before' this one (in arbitrary order); this method wraps around to the last screen.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.screen` object</li></ul>          |

| [rotate](#rotate)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:rotate([degrees]) -> bool or rotation angle`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets/Sets the rotation of a screen                                                                     |
| **Parameters**                              | <ul><li>degrees - An optional number indicating how many degrees clockwise, to rotate. If no number is provided, the current rotation will be returned. This number must be one of:</li><li> 0</li><li> 90</li><li> 180</li><li> 270</li></ul> |
| **Returns**                                 | <ul><li>If the rotation is being set, a boolean, true if the operation succeeded, otherwise false. If the rotation is being queried, a number will be returned</li></ul>          |

| [screen_desktopImageURL](#screen_desktopImageURL)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:screen_desktopImageURL([imageURL])`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets/Sets the desktop background image for a screen                                                                     |
| **Parameters**                              | <ul><li>imageURL - An optional file:// URL to an image file to set as the background. If omitted, the current file URL is returned</li></ul> |
| **Returns**                                 | <ul><li>the `hs.screen` object if a new URL was set, otherwise a string containing the current URL</li></ul>          |

| [setBrightness](#setBrightness)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:setBrightness(brightness) -> `hs.screen` object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the screen's brightness                                                                     |
| **Parameters**                              | <ul><li>brightness - A floating point number between 0 and 1</li></ul> |
| **Returns**                                 | <ul><li>The `hs.screen` object</li></ul>          |

| [setGamma](#setGamma)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:setGamma(whitepoint, blackpoint) -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the current white point and black point of the screen                                                                     |
| **Parameters**                              | <ul><li>whitepoint - A table containing color component values between 0.0 and 1.0 for each of the keys:</li><li> red</li><li> green</li><li> blue</li><li>blackpoint - A table containing color component values between 0.0 and 1.0 for each of the keys:</li><li> red</li><li> green</li><li> blue</li></ul> |
| **Returns**                                 | <ul><li>A boolean, true if the gamma settings were applied, false if an error occurred</li></ul>          |
| **Notes**                                   | <ul><li>If the whitepoint and blackpoint specified, are very similar, it will be impossible to read the screen. You should exercise caution, and may wish to bind a hotkey to `hs.screen.restoreGamma()` when experimenting</li></ul>                |

| [setMode](#setMode)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:setMode(width, height, scale) -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the screen to a new mode                                                                     |
| **Parameters**                              | <ul><li>width - A number containing the width in points of the new mode</li><li>height - A number containing the height in points of the new mode</li><li>scale - A number containing the scaling factor of the new mode (typically 1 for native pixel resolutions, 2 for HiDPI/Retina resolutions)</li></ul> |
| **Returns**                                 | <ul><li>A boolean, true if the requested mode was set, otherwise false</li></ul>          |
| **Notes**                                   | <ul><li>The available widths/heights/scales can be seen in the output of `hs.screen:availableModes()`, however, it should be noted that the CoreGraphics subsystem seems to list more modes for a given screen than it is actually prepared to set, so you may find that seemingly valid modes still return false. It is not currently understood why this is so!</li></ul>                |

| [setPrimary](#setPrimary)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:setPrimary() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the screen to be the primary display (i.e. contain the menubar and dock)                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A boolean, true if the operation succeeded, otherwise false</li></ul>          |

| [shotAsJPG](#shotAsJPG)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:shotAsJPG(filePath[, screenRect])`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Saves an image of the screen to a JPG file                                                                     |
| **Parameters**                              | <ul><li>filePath - A string containing a file path to save the screenshot as</li><li>screenRect - An optional `hs.geometry` rect (or arguments for its constructor) containing a portion of the screen to capture. Defaults to the whole screen</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [shotAsPNG](#shotAsPNG)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:shotAsPNG(filePath[, screenRect])`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Saves an image of the screen to a PNG file                                                                     |
| **Parameters**                              | <ul><li>filePath - A string containing a file path to save the screenshot as</li><li>screenRect - An optional `hs.geometry` rect (or arguments for its constructor) containing a portion of the screen to capture. Defaults to the whole screen</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [snapshot](#snapshot)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:snapshot([rect]) -> object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Captures an image of the screen                                                                     |
| **Parameters**                              | <ul><li>rect - An optional `rect-table` containing a portion of the screen to capture. Defaults to the whole screen</li></ul> |
| **Returns**                                 | <ul><li>An `hs.image` object, or nil if an error occurred</li></ul>          |

| [toEast](#toEast)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:toEast() -> hs.screen object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the first screen to the east of this one, ordered by proximity to its center or a specified point.                                                                     |
| **Parameters**                              | <ul><li> from - An `hs.geometry.rect` or `hs.geometry.point` object; if omitted, the geometric center of this screen will be used</li><li> strict - If `true`, disregard screens that lie completely above or below this one (alternatively, set `hs.screen.strictScreenInDirection`)</li></ul> |
| **Returns**                                 | <ul><li> An `hs.screen` object, or `nil` if not found</li></ul>          |

| [toNorth](#toNorth)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:toNorth() -> hs.screen object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the first screen to the north of this one, ordered by proximity to its center or a specified point.                                                                     |
| **Parameters**                              | <ul><li> from - An `hs.geometry.rect` or `hs.geometry.point` object; if omitted, the geometric center of this screen will be used</li><li> strict - If `true`, disregard screens that lie completely to the left or to the right of this one (alternatively, set `hs.screen.strictScreenInDirection`)</li></ul> |
| **Returns**                                 | <ul><li> An `hs.screen` object, or `nil` if not found</li></ul>          |

| [toSouth](#toSouth)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:toSouth() -> hs.screen object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the first screen to the south of this one, ordered by proximity to its center or a specified point.                                                                     |
| **Parameters**                              | <ul><li> from - An `hs.geometry.rect` or `hs.geometry.point` object; if omitted, the geometric center of this screen will be used</li><li> strict - If `true`, disregard screens that lie completely to the left or to the right of this one (alternatively, set `hs.screen.strictScreenInDirection`)</li></ul> |
| **Returns**                                 | <ul><li> An `hs.screen` object, or `nil` if not found</li></ul>          |

| [toUnitRect](#toUnitRect)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:toUnitRect(rect) -> hs.geometry unitrect`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the unit rect of a given rect, relative to this screen                                                                     |
| **Parameters**                              | <ul><li>rect - an hs.geometry rect, or arguments to construct one</li></ul> |
| **Returns**                                 | <ul><li>an hs.geometry unit rect describing the given rect relative to this screen's frame</li></ul>          |
| **Notes**                                   | <ul><li>this method is just a convenience wrapper for `hs.geometry.toUnitRect(rect,this_screen:frame())`</li></ul>                |

| [toWest](#toWest)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.screen:toWest() -> hs.screen object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the first screen to the west of this one, ordered by proximity to its center or a specified point.                                                                     |
| **Parameters**                              | <ul><li> from - An `hs.geometry.rect` or `hs.geometry.point` object; if omitted, the geometric center of this screen will be used</li><li> strict - If `true`, disregard screens that lie completely above or below this one (alternatively, set `hs.screen.strictScreenInDirection`)</li></ul> |
| **Returns**                                 | <ul><li> An `hs.screen` object, or `nil` if not found</li></ul>          |
