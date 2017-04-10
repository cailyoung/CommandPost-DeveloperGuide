# Hammerspoon docs: hs.keycodes

Convert between key-strings and key-codes. Also provides funcionality for querying and changing keyboard layouts.

## API Overview
* Constants - Useful values which cannot be changed</li>
  * map
* Functions - API calls offered directly by the extension</li>
  * currentLayout
  * currentLayoutIcon
  * currentMethod
  * currentSourceID
  * iconForLayoutOrMethod
  * inputSourceChanged
  * layouts
  * methods
  * setLayout
  * setMethod

## API Documentation

### Constants

#### map
  * Signature: hs.keycodes.map
  * Type: Constant
  * Description: A mapping from string representation of a key to its keycode, and vice versa.
  For example: keycodes[1] == "s", and keycodes["s"] == 1, and so on.
    This is primarily used by the hs.eventtap and hs.hotkey extensions.
    Valid strings are any single-character string, or any of the following strings:
        f1, f2, f3, f4, f5, f6, f7, f8, f9, f10, f11, f12, f13, f14, f15,
        f16, f17, f18, f19, f20, pad, pad*, pad+, pad/, pad-, pad=,
        pad0, pad1, pad2, pad3, pad4, pad5, pad6, pad7, pad8, pad9,
        padclear, padenter, return, tab, space, delete, escape, help,
        home, pageup, forwarddelete, end, pagedown, left, right, down, up

### Functions

#### currentLayout
  * Signature: hs.keycodes.currentLayout() -> string
  * Type: Function
  * Description: Gets the name of the current keyboard layout
  * Parameters:
     * None
  * Returns:
     * A string containing the name of the current keyboard layout

#### currentLayoutIcon
  * Signature: hs.keycodes.currentLayoutIcon() -> hs.image object
  * Type: Function
  * Description: Gets the icon of the current keyboard layout
  * Parameters:
     * None
  * Returns:
     * An hs.image object containing the icon, if available

#### currentMethod
  * Signature: hs.keycodes.currentMethod() -> string
  * Type: Function
  * Description: Get current input method
  * Parameters:
     * None
  * Returns:
     * Name of current input method, or nil

#### currentSourceID
  * Signature: hs.keycodes.currentSourceID([sourceID]) -> string | boolean
  * Type: Function
  * Description: Get or set the source id for the keyboard input source
  * Parameters:
     * sourceID - an optional string specifying the input source to set for keyboard input
  * Returns:
     * If no parameter is provided, returns a string containing the source id for the current keyboard layout or input method; if a parameter is provided, returns true or false specifying whether or not the input source was able to be changed.

#### iconForLayoutOrMethod
  * Signature: hs.keycodes.iconForLayoutOrMethod(sourceName) -> hs.image object
  * Type: Function
  * Description: Gets an hs.image object for a given keyboard layout or input method
  * Parameters:
     * sourceName - A string containing the name of an input method or keyboard layout
  * Returns:
     * An hs.image object, or nil if no image could be found
  * Notes:
     * Not all layouts/methods have icons, so you should assume this will return nil at some point

#### inputSourceChanged
  * Signature: hs.keycodes.inputSourceChanged(fn)
  * Type: Function
  * Description: Sets the function to be called when your input source (i.e. qwerty, dvorak, colemac) changes.
  * Parameters:
     * fn - A function that will be called when the input source changes. No arguments are supplied to the function.
  * Returns:
     * None
  * Notes:
     * This may be helpful for rebinding your hotkeys to appropriate keys in the new layout
     * Setting this will un-set functions previously registered by this function.

#### layouts
  * Signature: hs.keycodes.layouts([sourceID]) -> table
  * Type: Function
  * Description: Gets all of the enabled keyboard layouts that the keyboard input source can be switched to
  * Parameters:
     * sourceID - an optional boolean, default false, indicating whether the keyboard layout names should be returned (false) or their source IDs (true).
  * Returns:
     * A table containing a list of keyboard layouts enabled in System Preferences
  * Notes:
     * Only those layouts which can be explicitly switched to will be included in the table.  Keyboard layouts which are part of input methods are not included.  See `hs.keycodes.methods`.

#### methods
  * Signature: hs.keycodes.methods([sourceID]) -> table
  * Type: Function
  * Description: Gets all of the enabled input methods that the keyboard input source can be switched to
  * Parameters:
     * sourceID - an optional boolean, default false, indicating whether the keyboard input method names should be returned (false) or their source IDs (true).
  * Returns:
     * A table containing a list of input methods enabled in System Preferences
  * Notes:
     * Keyboard layouts which are not part of an input method are not included in this table.  See `hs.keycodes.layouts`.

#### setLayout
  * Signature: hs.keycodes.setLayout(layoutName) -> boolean
  * Type: Function
  * Description: Changes the system keyboard layout
  * Parameters:
     * layoutName - A string containing the name of an enabled keyboard layout
  * Returns:
     * A boolean, true if the layout was successfully changed, otherwise false

#### setMethod
  * Signature: hs.keycodes.setMethod(methodName) -> boolean
  * Type: Function
  * Description: Changes the system input method
  * Parameters:
     * methodName - A string containing the name of an enabled input method
  * Returns:
     * A boolean, true if the method was successfully changed, otherwise false