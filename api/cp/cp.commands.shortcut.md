# [docs](index.md) » cp.commands.shortcut
---

Shortcut Commands

## Submodules
 * [cp.commands.shortcut.builder](cp.commands.shortcut.builder.md)

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [bind](#bind)
 * [build](#build)
 * [enable](#enable)
 * [new](#new)
 * [trigger](#trigger)

## API Documentation

### Methods

| [bind](#bind)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.commands.shortcut:bind(pressedFn, releasedFn, repeatedFn) -> shortcut`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | This function binds the shortcut to a hotkey, with the specified callback functions for `pressedFn`, `releasedFn` and `repeatedFn`.                                                                     |
| **Parameters**                              | <ul><li>`pressedFn`	- (optional) If present, this is called when the shortcut combo is pressed.</li><li>`releasedFn`	- (optional) If present, this is called when the shortcut combo is released.</li><li>`repeatedFn`	- (optional) If present, this is called when the shortcut combo is repeated.</li></ul> |
| **Returns**                                 | <ul><li>`self`</li></ul>          |
| **Notes**                                   | <ul><li>If the shortcut is enabled, the hotkey will also be enabled at this point.</li></ul>                |

| [build](#build)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.commands.shortcut:build(receiverFn) -> cp.commands.shortcut.builder`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Creates a new shortcut builder.                                                                     |
| **Parameters**                              | <ul><li>`receiverFn`		- (optional) a function which will get passed the shortcut when the build is complete.</li></ul> |
| **Returns**                                 | <ul><li>`shortcut.builder` which can be used to create the shortcut.</li></ul>          |
| **Notes**                                   | <ul><li>* If provided, the receiver function will be called when the shortcut has been configured, and passed the new</li><li>  shortcut. The result of that function will be returned to the next stage.</li><li>  If no `receiverFn` is provided, the shortcut will be returned directly.</li></ul>                |

| [enable](#enable)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.commands.shortcut:enable() - > shortcut`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | This enables the shortcut. If a hotkey has been bound, it will be enabled also.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`self`</li></ul>          |

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.commands.shortcut:new(command) -> shortcut`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Creates a new keyboard shortcut, attached to the specified `hs.commands.command`                                                                     |
| **Parameters**                              | <ul><li>`modifiers` 	- The modifiers.</li><li>`keyCode`	- The key code.</li></ul> |
| **Returns**                                 | <ul><li>shortcut - The shortcut that was created.</li></ul>          |

| [trigger](#trigger)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.commands.shortcut:trigger() -> shortcut`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | This will trigger the keystroke specified in the shortcut.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>`self`</li></ul>          |
