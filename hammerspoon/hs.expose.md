# Hammerspoon docs: hs.expose

Keyboard-driven expose replacement/enhancement

Warning: this module is still somewhat experimental.
Should you encounter any issues, please feel free to report them on https://github.com/Hammerspoon/hammerspoon/issues
or #hammerspoon on irc.freenode.net

With this module you can configure a hotkey to show thumbnails for open windows when invoked; each thumbnail will have
an associated keyboard "hint" (usually one or two characters) that you can type to quickly switch focus to that
window; in conjunction with keyboard modifiers, you can additionally minimize (`alt` by default) or close
(`shift` by default) any window without having to focus it first.

When used in combination with a windowfilter you can include or exclude specific apps, window titles, screens,
window roles, etc. Additionally, each expose instance can be customized to include or exclude minimized or hidden windows,
windows residing in other Mission Control Spaces, or only windows for the current application. You can further customize
hint length, colors, fonts and sizes, whether to show window thumbnails and/or titles, and more.

To improve responsiveness, this module will update its thumbnail layout in the background (so to speak), so that it
can show the expose without delay on invocation. Be aware that on particularly heavy Hammerspoon configurations
this could adversely affect overall performance; you can disable this behaviour with
`hs.expose.ui.fitWindowsInBackground=false`

Usage:
```
-- set up your instance(s)
expose = hs.expose.new(nil,{showThumbnails=false}) -- default windowfilter, no thumbnails
expose_app = hs.expose.new(nil,{onlyActiveApplication=true}) -- show windows for the current application
expose_space = hs.expose.new(nil,{includeOtherSpaces=false}) -- only windows in the current Mission Control Space
expose_browsers = hs.expose.new{'Safari','Google Chrome'} -- specialized expose using a custom windowfilter
-- for your dozens of browser windows :)

-- then bind to a hotkey
hs.hotkey.bind('ctrl-cmd','e','Expose',function()expose:toggleShow()end)
hs.hotkey.bind('ctrl-cmd-shift','e','App Expose',function()expose_app:toggleShow()end)
```

## API Overview
* Variables - Configurable values</li>
  * ui
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * new
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * hide
  * show
  * toggleShow

## API Documentation

### Variables

#### ui
  * Signature: hs.expose.ui
  * Type: Variable
  * Description: Allows customization of the expose behaviour and user interface
  This table contains variables that you can change to customize the behaviour of the expose and the look of the UI.
    To have multiple expose instances with different behaviour/looks, use the `uiPrefs` parameter for the constructor;
    the passed keys and values will override those in this table for that particular instance.
    The default values are shown in the right hand side of the assignements below.
    To represent color values, you can use:
     * a table {red=redN, green=greenN, blue=blueN, alpha=alphaN}
     * a table {redN,greenN,blueN[,alphaN]} - if omitted alphaN defaults to 1.0
    where redN, greenN etc. are the desired value for the color component between 0.0 and 1.0
     * `hs.expose.ui.textColor = {0.9,0.9,0.9}`
     * `hs.expose.ui.fontName = 'Lucida Grande'`
     * `hs.expose.ui.textSize = 40` - in screen points
     * `hs.expose.ui.highlightColor = {0.8,0.5,0,0.1}` - highlight color for candidate windows
     * `hs.expose.ui.backgroundColor = {0.30,0.03,0.03,1}`
     * `hs.expose.ui.closeModeModifier = 'shift'` - "close mode" engaged while pressed (or 'cmd','ctrl','alt')
     * `hs.expose.ui.closeModeBackgroundColor = {0.7,0.1,0.1,1}` - background color while "close mode" is engaged
     * `hs.expose.ui.minimizeModeModifier = 'alt'` - "minimize mode" engaged while pressed
     * `hs.expose.ui.minimizeModeBackgroundColor = {0.1,0.2,0.3,1}` - background color while "minimize mode" is engaged
     * `hs.expose.ui.onlyActiveApplication = false` -- only show windows of the active application
     * `hs.expose.ui.includeNonVisible = true` - include minimized and hidden windows
     * `hs.expose.ui.nonVisibleStripBackgroundColor = {0.03,0.1,0.15,1}` - contains hints for non-visible windows
     * `hs.expose.ui.nonVisibleStripPosition = 'bottom'` - set it to your Dock position ('bottom', 'left' or 'right')
     * `hs.expose.ui.nonVisibleStripWidth = 0.1` - 0..0.5, width of the strip relative to the screen
     * `hs.expose.ui.includeOtherSpaces = true` - include windows in other Mission Control Spaces
     * `hs.expose.ui.otherSpacesStripBackgroundColor = {0.1,0.1,0.1,1}`
     * `hs.expose.ui.otherSpacesStripPosition = 'top'`
     * `hs.expose.ui.otherSpacesStripWidth = 0.2`
     * `hs.expose.ui.showTitles = true` - show window titles
     * `hs.expose.ui.showThumbnails = true` - show window thumbnails
     * `hs.expose.ui.thumbnailAlpha = 0` - 0..1, opacity for thumbnails
     * `hs.expose.ui.highlightThumbnailAlpha = 1` - 0..1, opacity for thumbnails of candidate windows
     * `hs.expose.ui.highlightThumbnailStrokeWidth = 8` - thumbnail frame thickness for candidate windows
     * `hs.expose.ui.maxHintLetters = 2` - if necessary, hints longer than this will be disambiguated with digits
     * `hs.expose.ui.fitWindowsMaxIterations = 30` -- lower is faster, but higher chance of overlapping thumbnails
     * `hs.expose.ui.fitWindowsInBackground = false` -- improves responsivenss, but can affect the rest of the config

### Constructors

#### new
  * Signature: hs.expose.new([windowfilter[, uiPrefs][, logname, [loglevel]]]) -> hs.expose object
  * Type: Constructor
  * Description: Creates a new hs.expose instance; it can use a windowfilter to determine which windows to show
  * Parameters:
     * windowfilter - (optional) if omitted or nil, use the default windowfilter; otherwise it must be a windowfilter
       instance or constructor table
     * uiPrefs - (optional) a table to override UI preferences for this instance; its keys and values
       must follow the conventions described in `hs.expose.ui`; this parameter allows you to have multiple
       expose instances with different behaviour (for example, with and without thumbnails and/or titles)
       using different hotkeys
     * logname - (optional) name of the `hs.logger` instance for the new expose; if omitted, the class logger will be used
     * loglevel - (optional) log level for the `hs.logger` instance for the new expose
  * Returns:
     * the new instance
  * Notes:
      * by default expose will show invisible windows and (unlike the OSX expose) windows from other spaces; use
        `hs.expose.ui` or the `uiPrefs` parameter to change these behaviours.

### Methods

#### hide
  * Signature: hs.expose:hide()
  * Type: Method
  * Description: Hides the expose, if visible, and exits the modal mode.
  Call this function if you need to make sure the modal is exited without waiting for the user to press `esc`.
  * Parameters:
     * None
  * Returns:
     * None

#### show
  * Signature: hs.expose:show([activeApplication])
  * Type: Method
  * Description: Shows an expose-like screen with modal keyboard hints for switching to, closing or minimizing/unminimizing windows.
  * Parameters:
     * activeApplication - (optional) if true, only show windows of the active application (within the
      scope of the instance windowfilter); otherwise show all windows allowed by the instance windowfilter
  * Returns:
     * None
  * Notes:
     * passing `true` for `activeApplication` will simply hide hints/thumbnails for applications other
       than the active one, without recalculating the hints layout; conversely, setting `onlyActiveApplication=true`
       for an expose instance's `ui` will calculate an optimal layout for the current active application's windows
     * Completing a hint will exit the expose and focus the selected window.
     * Pressing esc will exit the expose and with no action taken.
     * If shift is being held when a hint is completed (the background will be red), the selected
       window will be closed. If it's the last window of an application, the application will be closed.
     * If alt is being held when a hint is completed (the background will be blue), the selected
       window will be minimized (if visible) or unminimized/unhidden (if minimized or hidden).

#### toggleShow
  * Signature: hs.expose:toggleShow([activeApplication])
  * Type: Method
  * Description: Toggles the expose - see `hs.expose:show()` and `hs.expose:hide()`
  Parameters: see `hs.expose:show()`
  * Returns:
     * None