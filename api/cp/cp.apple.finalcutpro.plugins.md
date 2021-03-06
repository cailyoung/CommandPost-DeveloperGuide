# [docs](index.md) » cp.apple.finalcutpro.plugins
---

Scan Final Cut Pro bundle for Effects, Generators, Titles & Transitions.

Usage:
require("cp.apple.finalcutpro"):plugins():scan()

## API Overview
* Constants - Useful values which cannot be changed
 * [appBuiltinPlugins](#appbuiltinplugins)
 * [appEdelEffects](#appedeleffects)
 * [audioUnitsCache](#audiounitscache)
 * [coreAudioPreferences](#coreaudiopreferences)
 * [types](#types)
* Functions - API calls offered directly by the extension
 * [clearCaches](#clearcaches)
 * [scan](#scan)
* Methods - API calls which can only be made on an object returned by a constructor
 * [audioEffects](#audioeffects)
 * [generators](#generators)
 * [ofType](#oftype)
 * [registerPlugin](#registerplugin)
 * [scanAll](#scanall)
 * [scanPluginsDirectory](#scanpluginsdirectory)
 * [titles](#titles)
 * [transitions](#transitions)
 * [videoEffects](#videoeffects)
 * [watch](#watch)

## API Documentation

### Constants

#### [appBuiltinPlugins](#appbuiltinplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.appBuiltinPlugins` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of built-in plugins                                                                                         |

#### [appEdelEffects](#appedeleffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.appEdelEffects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of Built-in Soundtrack Pro EDEL Effects.                                                                                         |

#### [audioUnitsCache](#audiounitscache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.audioUnitsCache` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Path to the Audio Units Cache                                                                                         |

#### [coreAudioPreferences](#coreaudiopreferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.coreAudioPreferences` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Core Audio Preferences File Path                                                                                         |

#### [types](#types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.types` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of the different Motion Template Extensions                                                                                         |

### Functions

#### [clearCaches](#clearcaches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.clearCaches() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears any local caches created for tracking the plugins.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the caches have been cleared successfully.</li></ul>          |

#### [scan](#scan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scan() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Scans Final Cut Pro for Effects, Transitions, Generators & Titles                                                                                         |
| **Parameters**                                       | <ul><li>fcp - the `cp.apple.finalcutpro` instance</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Methods

#### [audioEffects](#audioeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:audioEffects([language]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the 'audio effect' plugins.                                                                                         |
| **Parameters**                                       | <ul><li>* `language`	- The language code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>* A table of the available plugins.</li></ul>          |

#### [generators](#generators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:generators([language]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the 'generator' plugins.                                                                                         |
| **Parameters**                                       | <ul><li>* `language`	- The language code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>* A table of the available plugins.</li></ul>          |

#### [ofType](#oftype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:ofType(type[, language]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the plugins of the specified type (`types.videoEffect`, etc.) and if provided, language.                                                                                         |
| **Parameters**                                       | <ul><li>* `type`		- The plugin type. See `types` for the complete list.</li><li>* `language`	- The language code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>* A table of the available plugins of the specified type.</li></ul>          |

#### [registerPlugin](#registerplugin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:registerPlugin(path, type, categoryName, themeName, pluginName, language) -> plugin` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers a plugin with the specified details.                                                                                         |
| **Parameters**                                       | <ul><li>`path`			- The path to the plugin directory.</li><li>`type`			- The type of plugin</li><li>`categoryName`	- The category name, in the specified language.</li><li>`themeName`		- The theme name, in the specified language. May be `nil` if not in a theme.</li><li>`pluginName`		- The plugin name, in the specified language.</li><li>`language`		- The language code (e.g. "en", "fr", "de")</li></ul> |

#### [scanAll](#scanall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanAll() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Scans all supported languages, loading them into memory.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

#### [scanPluginsDirectory](#scanpluginsdirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanPluginsDirectory(language, path, filter) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Scans a root plugins directory. Plugins directories have a standard structure which comes in two flavours:                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to scan for (e.g. "en" or "fr").</li><li>`path`		- The path of the root plugin directory to scan.</li><li>`checkFn`		- A function which will receive the path being scanned and return `true` if it should be scanned.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the plugin directory was successfully scanned.</li></ul>          |

#### [titles](#titles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:titles([language]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the 'title' plugins.                                                                                         |
| **Parameters**                                       | <ul><li>* `language`	- The language code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>* A table of the available plugins.</li></ul>          |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:transitions([language]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the 'transitions' plugins.                                                                                         |
| **Parameters**                                       | <ul><li>* `language`	- The language code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>* A table of the available plugins.</li></ul>          |

#### [videoEffects](#videoeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:videoEffects([language]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the 'video effect' plugins.                                                                                         |
| **Parameters**                                       | <ul><li>* `language`	- The language code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>* A table of the available plugins.</li></ul>          |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:watch(events) -> id` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a watcher for the provided events table. The table can have the following functions:                                                                                         |

