# Summary

## Getting Started

* [Introduction](README.md)
* [Installation & Setup](getting_started/install/README.md)

## Lua

* [Lua Overview](lua/overview/README.md)

## Contributing

* [Naming Conventions](contributing/naming_conventions/README.md)
* [CommandPost-App](contributing/commandpost-app/README.md)
* [CommandPost](contributing/commandpost/README.md)

## Control CommandPost

* [AppleScript](control/applescript/README.md)
* [Command Line Tool](control/commandline/README.md)
* [URL Handler](control/urlhandler/README.md)

## Plugins

* [Plugins Overview](plugins/overview/README.md)

## Internationalisation

* [Translating CommandPost](internationalisation/translate/README.md)

## Final Cut Pro

* [FCPXML](final_cut_pro/fcpxml/README.md)
* [iXML](final_cut_pro/ixml/README.md)
* [Package Contents](final_cut_pro/package_contents/README.md)

## Bundled Extensions

* [axuielement](api/axuielement/Reference.md)
* [gambiarra](api/gambiarra/README.md)
* [i18n](api/i18n/README.md)
* [mimetypes](api/mimetypes/README.md)
* [moses](api/moses/README.md)
* [resty](api/resty/README.md)
* [semver](api/semver/README.md)
* [slaxml](api/slaxml/README.md)
* [touchbar](api/touchbar/README.md)

## CommandPost API

* [cp](api/cp/cp.md)
	* apple
		* [compressor](api/cp/cp.compressor.md)
		* [finalcutpro](api/cp/cp.apple.finalcutpro.md)
			* cmd
				* [CommandEditor](api/cp/cp.apple.finalcutpro.cmd.CommandEditor.md)
			* content
				* [Clip](api/cp/cp.apple.finalcutpro.content.Clip.md)
			* [destinations](api/cp/cp.apple.finalcutpro.destinations.md)
			* export
				* [destinations](api/cp/cp.apple.finalcutpro.export.destinations.md)
				* [ExportDialog](api/cp/cp.apple.finalcutpro.export.ExportDialog.md)
				* [GoToPrompt](api/cp/cp.apple.finalcutpro.export.GoToPrompt.md)
				* [ReplaceAlert](api/cp/cp.apple.finalcutpro.export.ReplaceAlert.md)
				* [SaveSheet](api/cp/cp.apple.finalcutpro.export.SaveSheet.md)
			* import
				* [MediaImport](api/cp/cp.apple.finalcutpro.import.MediaImport.md)
			* [keycodes](api/cp/cp.apple.finalcutpro.keycodes.md)
			* main
				* [Browser](api/cp/cp.apple.finalcutpro.main.Browser.md)
				* [ColorBoard](api/cp/cp.apple.finalcutpro.main.ColorBoard.md)
				* [ColorPucker](api/cp/cp.apple.finalcutpro.main.ColorPucker.md)
				* [EffectsBrowser](api/cp/cp.apple.finalcutpro.main.EffectsBrowser.md)
				* [FullScreenWindow](api/cp/cp.apple.finalcutpro.main.FullScreenWindow.md)
				* [GeneratorsBrowser](api/cp/cp.apple.finalcutpro.main.GeneratorsBrowser.md)
				* [Inspector](api/cp/cp.apple.finalcutpro.main.Inspector.md)
					* [AudioInspector](api/cp/cp.apple.finalcutpro.main.Inspector.AudioInspector.md)
					* [ColorInspector](api/cp/cp.apple.finalcutpro.main.Inspector.ColorInspector.md)
						* [ColorBoard](api/cp/cp.apple.finalcutpro.main.Inspector.ColorInspector.ColorBoard.md)
						* [ColorCurves](api/cp/cp.apple.finalcutpro.main.Inspector.ColorInspector.ColorCurves.md)
						* [ColorWheels](api/cp/cp.apple.finalcutpro.main.Inspector.ColorInspector.ColorWheels.md)
						* [HueSaturationCurves](api/cp/cp.apple.finalcutpro.main.Inspector.ColorInspector.HueSaturationCurves.md)
					* [EffectInspector](api/cp/cp.apple.finalcutpro.main.Inspector.EffectInspector.md)
					* [GeneratorInspector](api/cp/cp.apple.finalcutpro.main.Inspector.GeneratorInspector.md)
					* [InfoInspector](api/cp/cp.apple.finalcutpro.main.Inspector.InfoInspector.md)
					* [ShareInspector](api/cp/cp.apple.finalcutpro.main.Inspector.ShareInspector.md)
					* [TextInspector](api/cp/cp.apple.finalcutpro.main.Inspector.TextInspector.md)
					* [TitleInspector](api/cp/cp.apple.finalcutpro.main.Inspector.TitleInspector.md)
					* [TransitionInspector](api/cp/cp.apple.finalcutpro.main.Inspector.TransitionInspector.md)
					* [VideoInspector](api/cp/cp.apple.finalcutpro.main.Inspector.AudioInspector.md)
				* [LibrariesBrowser](api/cp/cp.apple.finalcutpro.main.LibrariesBrowser.md)
				* [LibrariesFilmstrip](api/cp/cp.apple.finalcutpro.main.LibrariesFilmstrip.md)
				* [LibrariesList](api/cp/cp.apple.finalcutpro.main.LibrariesList.md)
				* [MediaBrowser](api/cp/cp.apple.finalcutpro.main.MediaBrowser.md)
				* [Playhead](api/cp/cp.apple.finalcutpro.main.Playhead.md)
				* [PrimaryWindow](api/cp/cp.apple.finalcutpro.main.PrimaryWindow.md)
				* [SecondaryWindow](api/cp/cp.apple.finalcutpro.main.SecondaryWindow.md)
				* [Timeline](api/cp/cp.apple.finalcutpro.main.Timeline.md)
				* [TimelineAppearance](api/cp/cp.apple.finalcutpro.main.TimelineAppearance.md)
				* [TimelineContents](api/cp/cp.apple.finalcutpro.main.TimelineContents.md)
				* [TimelineToolbar](api/cp/cp.apple.finalcutpro.main.TimelineToolbar.md)
				* [Viewer](api/cp/cp.apple.finalcutpro.main.Viewer.md)
			* [MenuBar](api/cp/cp.apple.finalcutpro.MenuBar.md)
			* [plugins](api/cp/cp.apple.finalcutpro.plugins.md)
			* prefs
				* [ImportPanel](api/cp/cp.apple.finalcutpro.prefs.ImportPanel.md)
				* [PlaybackPanel](api/cp/cp.apple.finalcutpro.prefs.PlaybackPanel.md)
				* [PreferencesWindow](api/cp/cp.apple.finalcutpro.prefs.PreferencesWindow.md)
			* [WindowWatcher](api/cp/cp.apple.finalcutpro.WindowWatcher.md)
	* [bench](api/cp/cp.bench.md)
	* [choices](api/cp/cp.choices.md)
		* [builder](api/cp/cp.choices.builder.md)
	* [commands](api/cp/cp.commands.md)
		* [command](api/cp/cp.commands.command.md)
		* [englishKeyCodes](api/cp/cp.commands.englishKeyCodes.md)
		* [shortcut](api/cp/cp.commands.shortcut.md)
			* [builder](api/cp/cp.commands.shortcut.builder.md)
	* [config](api/cp/cp.config.md)
		* [accessibilityStateCallback](api/cp/cp.config.accessibilityStateCallback.md)
		* [dockIconClickCallback](api/cp/cp.config.dockIconClickCallback.md)
		* [fileDroppedToDockIconCallback](api/cp/cp.config.fileDroppedToDockIconCallback.md)
		* [shutdownCallback](api/cp/cp.config.shutdownCallback.md)
		* [textDroppedToDockIconCallback](api/cp/cp.config.textDroppedToDockIconCallback.md)
	* [developer](api/cp/cp.developer.md)
	* [dialog](api/cp/cp.dialog.md)
	* [feedback](api/cp/cp.feedback.md)
	* [ids](api/cp/cp.ids.md)
	* [idle](api/cp/cp.idle.md)
	* [just](api/cp/cp.just.md)
	* [localized](api/cp/cp.localized.md)
	* [plist](api/cp/cp.plist.md)
		* [archiver](api/cp/cp.plist.archiver.md)
	* [plugins](api/cp/cp.plugins.md)
		* [env](api/cp/cp.plugins.env.md)
	* [prop](api/cp/cp.prop.md)
	* [sourcewatcher](api/cp/cp.sourcewatcher.md)
	* [strings](api/cp/cp.strings.md)
		* source
			* [plist](api/cp/cp.strings.source.plist.md)
			* [table](api/cp/cp.strings.source.table.md)
	* [text](api/cp/cp.text.md)
		* [matcher](api/cp/cp.text.matcher.md)
	* [tools](api/cp/cp.tools.md)
	* [ui](api/cp/cp.ui.md)
		* [Alert](api/cp/cp.ui.Alert.md)
		* [axutils](api/cp/cp.ui.axutils.md)
		* [Button](api/cp/cp.ui.Button.md)
		* [CheckBox](api/cp/cp.ui.CheckBox.md)
		* [PopUpButton](api/cp/cp.ui.PopUpButton.md)
		* [RadioButton](api/cp/cp.ui.RadioButton.md)
		* [ScrollArea](api/cp/cp.ui.ScrollArea.md)
		* [Slider](api/cp/cp.ui.Slider.md)
		* [Table](api/cp/cp.ui.Table.md)
		* [TextField](api/cp/cp.ui.TextField.md)
		* [Window](api/cp/cp.ui.Window.md)
	* [utf16](api/cp/cp.utf16.md)
		* [be](api/cp/cp.utf16.be.md)
		* [le](api/cp/cp.utf16.le.md)
	* [watcher](api/cp/cp.watcher.md)
	* web
		* [generate](api/cp/cp.web.generate.md)
		* [html](api/cp/cp.web.html.md)
		* [text](api/cp/cp.web.text.md)
		* [ui](api/cp/cp.web.ui.md)

## Bundled Plugins API

* [plugins](api/plugins/index.md)
	* core
		* [accessibility](api/plugins/plugins.core.accessibility.md)
		* action
			* [activator](api/plugins/plugins.core.action.activator.md)
			* [handler](api/plugins/plugins.core.action.handler.md)
			* [manager](api/plugins/plugins.core.action.manager.md)
		* commands
			* [actions](api/plugins/plugins.core.commands.actions.md)
			* [commandaction](api/plugins/plugins.core.commands.commandaction.md)
			* [global](api/plugins/plugins.core.commands.global.md)
		* [console](api/plugins/plugins.core.console.md)
		* helpandsupport
			* [credits](api/plugins/plugins.core.helpandsupport.credits.md)
			* [feedback](api/plugins/plugins.core.helpandsupport.feedback.md)
			* [userguide](api/plugins/plugins.core.helpandsupport.userguide.md)
		* [language](api/plugins/plugins.core.language.md)
		* menu
			* [bottom](api/plugins/plugins.core.menu.bottom.md)
			* [helpandsupport](api/plugins/plugins.core.menu.helpandsupport.md)
				* [commandpost](api/plugins/plugins.core.menu.helpandsupport.commandpost.md)
			* [manager](api/plugins/plugins.core.menu.manager.md)
				* [section](api/plugins/plugins.core.menu.manager.section.md)
			* [top](api/plugins/plugins.core.menu.top.md)
		* midi
			* [manager](api/plugins/plugins.core.midi.manager.md)
				* [controls](api/plugins/plugins.core.midi.manager.controls.md)
		* preferences
			* [advanced](api/plugins/plugins.core.preferences.advanced.md)
			* [general](api/plugins/plugins.core.preferences.general.md)
			* [manager](api/plugins/plugins.core.preferences.manager.md)
			* panels
				* [advanced](api/plugins/plugins.core.preferences.panels.advanced.md)
				* [general](api/plugins/plugins.core.preferences.panels.general.md)
				* [menubar](api/plugins/plugins.core.preferences.panels.menubar.md)
				* [midi](api/plugins/plugins.core.preferences.panels.midi.md)
				* [notifications](api/plugins/plugins.core.preferences.panels.notifications.md)
				* [plugins](api/plugins/plugins.core.preferences.panels.plugins.md)
				* [shortcuts](api/plugins/plugins.core.preferences.panels.shortcuts.md)
				* [streamdeck](api/plugins/plugins.core.preferences.panels.streamdeck.md)
				* [tangent](api/plugins/plugins.core.preferences.panels.tangent.md)
				* [touchbar](api/plugins/plugins.core.preferences.panels.touchbar.md)
				* [webapp](api/plugins/plugins.core.preferences.panels.webapp.md)
			* [updates](api/plugins/plugins.core.preferences.updates.md)
		* [quit](api/plugins/plugins.core.quit.md)
		* [setup](api/plugins/plugins.core.setup.md)
			* [panel](api/plugins/plugins.core.setup.panel.md)
		* streamdeck
			* [manager](api/plugins/plugins.core.streamdeck.manager.md)
		* touchbar
			* [manager](api/plugins/plugins.core.touchbar.manager.md)
				* [virtual](api/plugins/plugins.core.touchbar.manager.virtual.md)
					* [updateLocationCallback](api/plugins/plugins.core.touchbar.manager.virtual.updateLocationCallback.md)
				* [widgets](api/plugins/plugins.core.touchbar.manager.widgets.md)
				* widgets
					* [volume](api/plugins/plugins.core.touchbar.widgets.volume.md)
					* [windowSlide](api/plugins/plugins.core.touchbar.widgets.windowSlide.md)
		* watchfolders
			* [manager](api/plugins/plugins.core.watchfolders.manager.md)
				* [panel](api/plugins/plugins.core.watchfolders.manager.panel.md)
		* [webapp](api/plugins/plugins.core.webapp.md)
	* compressor
		* watchfolders
			* panels
				* [media](api/plugins/plugins.compressor.watchfolders.panels.media.md)
	* finalcutpro
		* commands
			* [actions](api/plugins/plugins.finalcutpro.commands.actions.md)
		* browser
			* [addnote](api/plugins/plugins.finalcutpro.browser.addnote.md)
			* [keywords](api/plugins/plugins.finalcutpro.browser.keywords.md)
			* [playhead](api/plugins/plugins.finalcutpro.browser.playhead.md)
		* clipboard
			* [history](api/plugins/plugins.finalcutpro.clipboard.history.md)
			* [manager](api/plugins/plugins.finalcutpro.clipboard.manager.md)
			* [shared](api/plugins/plugins.finalcutpro.clipboard.shared.md)
		* [commands](api/plugins/plugins.finalcutpro.commands.md)
		* [console](api/plugins/plugins.finalcutpro.console.md)
		* export
			* [batch](api/plugins/plugins.finalcutpro.export.batch.md)
		* feedback
			* [bugreport](api/plugins/plugins.finalcutpro.feedback.bugreport.md)
		* fullscreen
			* [shortcuts](api/plugins/plugins.finalcutpro.fullscreen.shortcuts.md)
		* hacks
			* [backupinterval](api/plugins/plugins.finalcutpro.hacks.backupinterval.md)
			* [movingmarkers](api/plugins/plugins.finalcutpro.hacks.movingmarkers.md)
			* [playbackrendering](api/plugins/plugins.finalcutpro.hacks.playbackrendering.md)
			* [shortcuts](api/plugins/plugins.finalcutpro.hacks.shortcuts.md)
			* [smartcollectionslabel](api/plugins/plugins.finalcutpro.hacks.smartcollectionslabel.md)
		* [hud](api/plugins/plugins.finalcutpro.hud.md)
		* import
			* [ignorecard](api/plugins/plugins.finalcutpro.import.ignorecard.md)
			* [preferences](api/plugins/plugins.finalcutpro.import.preferences.md)
		* [language](api/plugins/plugins.finalcutpro.language.md)
		* menu
			* [administrator](api/plugins/plugins.finalcutpro.menu.administrator.md)
				* [advancedfeatures](api/plugins/plugins.finalcutpro.menu.administrator.advancedfeatures.md)
			* [clipboard](api/plugins/plugins.finalcutpro.menu.clipboard.md)
			* helpandsupport
				* [finalcutpro](api/plugins/plugins.finalcutpro.menu.helpandsupport.finalcutpro.md)
			* [mediaimport](api/plugins/plugins.finalcutpro.menu.mediaimport.md)
			* [menuaction](api/plugins/plugins.finalcutpro.menu.menuaction.md)
			* [proxyicon](api/plugins/plugins.finalcutpro.menu.proxyicon.md)
			* [timeline](api/plugins/plugins.finalcutpro.menu.timeline.md)
				* [assignshortcuts](api/plugins/plugins.finalcutpro.menu.timeline.assignshortcuts.md)
			* [tools](api/plugins/plugins.finalcutpro.menu.tools.md)
				* [notifications](api/plugins/plugins.finalcutpro.menu.tools.notifications.md)
			* [top](api/plugins/plugins.finalcutpro.menu.top.md)
			* [viewer](api/plugins/plugins.finalcutpro.menu.viewer.md)
				* [showtimecode](api/plugins/plugins.finalcutpro.menu.viewer.showtimecode.md)
		* midi
			* controls
				* [colorboard](api/plugins/plugins.finalcutpro.midi.controls.colorboard.md)
				* [zoom](api/plugins/plugins.finalcutpro.midi.controls.zoom.md)
			* [manager](api/plugins/plugins.finalcutpro.midi.manager.md)
		* notifications
			* [imessage](api/plugins/plugins.finalcutpro.notifications.imessage.md)
			* [manager](api/plugins/plugins.finalcutpro.notifications.manager.md)
			* [prowl](api/plugins/plugins.finalcutpro.notifications.prowl.md)
			* [pushover](api/plugins/plugins.finalcutpro.notifications.pushover.md)
		* [open](api/plugins/plugins.finalcutpro.open.md)
		* os
			* [voice](api/plugins/plugins.finalcutpro.os.voice.md)
		* preferences
			* panels
				* [finalcutpro](api/plugins/plugins.finalcutpro.preferences.panels.finalcutpro.md)
			* [scanfinalcutpro](api/plugins/plugins.finalcutpro.preferences.scanfinalcutpro.md)
		* sharing
			* [xml](api/plugins/plugins.finalcutpro.sharing.xml.md)
		* [streamdeck](api/plugins/plugins.finalcutpro.streamdeck.md)
		* tangent
			[manager](api/plugins/plugins.finalcutpro.tangent.manager.md)
		* [text2speech](api/plugins/plugins.finalcutpro.text2speech.md)
		* timeline
			* [audioeffects](api/plugins/plugins.finalcutpro.timeline.audioeffects.md)
			* [colorboard](api/plugins/plugins.finalcutpro.timeline.colorboard.md)
			* [commandsetactions](api/plugins/plugins.finalcutpro.timeline.commandsetactions.md)
			* [disablewaveforms](api/plugins/plugins.finalcutpro.timeline.disablewaveforms.md)
			* [effects](api/plugins/plugins.finalcutpro.timeline.effects.md)
			* [generators](api/plugins/plugins.finalcutpro.timeline.generators.md)
			* [height](api/plugins/plugins.finalcutpro.timeline.height.md)
			* [lanes](api/plugins/plugins.finalcutpro.timeline.lanes.md)
			* [matchframe](api/plugins/plugins.finalcutpro.timeline.matchframe.md)
			* [mousezoom](api/plugins/plugins.finalcutpro.timeline.mousezoom.md)
			* [movetoplayhead](api/plugins/plugins.finalcutpro.timeline.movetoplayhead.md)
			* [multicam](api/plugins/plugins.finalcutpro.timeline.multicam.md)
			* [playback](api/plugins/plugins.finalcutpro.timeline.playback.md)
			* [playhead](api/plugins/plugins.finalcutpro.timeline.playhead.md)
			* [pluginactions](api/plugins/plugins.finalcutpro.timeline.pluginactions.md)
			* [pluginshortcuts](api/plugins/plugins.finalcutpro.timeline.pluginshortcuts.md)
			* [pluginshortcuts](api/plugins/plugins.finalcutpro.timeline.pluginshortcuts.md)
			* [preferences](api/plugins/plugins.finalcutpro.timeline.preferences.md)
			* [selectalltimelineclips](api/plugins/plugins.finalcutpro.timeline.selectalltimelineclips.md)
			* [stabilization](api/plugins/plugins.finalcutpro.timeline.stabilization.md)
			* [titles](api/plugins/plugins.finalcutpro.timeline.titles.md)
			* [transitions](api/plugins/plugins.finalcutpro.timeline.transitions.md)
			* [videoeffects](api/plugins/plugins.finalcutpro.timeline.videoeffects.md)
			* [zoomtoselection](api/plugins/plugins.finalcutpro.timeline.zoomtoselection.md)
		* touchbar
			* [virtual](api/plugins/plugins.finalcutpro.touchbar.virtual.md)
			* widgets
				* [colorboard](api/plugins/plugins.finalcutpro.touchbar.widgets.colorboard.md)
				* [zoom](api/plugins/plugins.finalcutpro.touchbar.widgets.zoom.md)
		* viewer
			* [showtimecode](api/plugins/plugins.finalcutpro.viewer.showtimecode.md)
			* [showtimelineinplayer](api/plugins/plugins.finalcutpro.viewer.showtimelineinplayer.md)
			* [timecodeoverlay](api/plugins/plugins.finalcutpro.viewer.timecodeoverlay.md)
		* watchfolders
			* panels
				* [fcpxml](api/plugins/plugins.finalcutpro.watchfolders.panels.fcpxml.md)
				* [media](api/plugins/plugins.finalcutpro.watchfolders.panels.media.md)
		* watchers
			* [preferences](api/plugins/plugins.finalcutpro.watchers.preferences.md)
			* [version](api/plugins/plugins.finalcutpro.watchers.version.md)

## Hammerspoon API

* [hs](api/hs/hs.md)
	* [alert](api/hs/hs.alert.md)
	* [appfinder](api/hs/hs.appfinder.md)
	* [applescript](api/hs/hs.applescript.md)
	* [application](api/hs/hs.application.md)
		* [watcher](api/hs/hs.application.watcher.md)
	* [audiodevice](api/hs/hs.audiodevice.md)
		* [datasource](api/hs/hs.audiodevice.datasource.md)
		* [watcher](api/hs/hs.audiodevice.watcher.md)
	* [base64](api/hs/hs.base64.md)
	* [battery](api/hs/hs.battery.md)
		* [watcher](api/hs/hs.battery.watcher.md)
	* [brightness](api/hs/hs.brightness.md)
	* [caffeinate](api/hs/hs.caffeinate.md)
		* [watcher](api/hs/hs.caffeinate.watcher.md)
	* [canvas](api/hs/hs.canvas.md)
		* [drawing](api/hs/hs.canvas.drawing.md)
		* [matrix](api/hs/hs.canvas.matrix.md)
	* [chooser](api/hs/hs.chooser.md)
	* [console](api/hs/hs.console.md)
	* [crash](api/hs/hs.crash.md)
	* [deezer](api/hs/hs.deezer.md)
	* [dialog](api/hs/hs.dialog.md)
	* [distributednotifications](api/hs/hs.distributednotifications.md)
	* [doc](api/hs/hs.doc.md)
		* [builder](api/hs/hs.doc.builder.md)
		* [hsdocs](api/hs/hs.doc.hsdocs.md)
		* [markdown](api/hs/hs.doc.markdown.md)
		* [spoonsupport](api/hs/hs.doc.spoonsupport.md)
	* [dockicon](api/hs/hs.dockicon.md)
	* [drawing](api/hs/hs.drawing.md)
		* [color](api/hs/hs.drawing.color.md)
	* [eventtap](api/hs/hs.eventtap.md)
		* [event](api/hs/hs.eventtap.event.md)
	* [expose](api/hs/hs.expose.md)
	* [fnutils](api/hs/hs.fnutils.md)
	* [fs](api/hs/hs.fs.md)
		* [volume](api/hs/hs.fs.volume.md)
	* [geometry](api/hs/hs.geometry.md)
	* [grid](api/hs/hs.grid.md)
	* [hash](api/hs/hs.hash.md)
	* [hints](api/hs/hs.hints.md)
	* [host](api/hs/hs.host.md)
		* [locale](api/hs/hs.host.locale.md)
	* [hotkey](api/hs/hs.hotkey.md)
		* [modal](api/hs/hs.hotkey.modal.md)
	* [http](api/hs/hs.http.md)
	* [httpserver](api/hs/hs.httpserver.md)
		* [hsminweb.cgilua.lp](api/hs/hs.httpserver.hsminweb.cgilua.lp.md)
		* [hsminweb.cgilua](api/hs/hs.httpserver.hsminweb.cgilua.md)
		* [hsminweb.cgilua.urlcode](api/hs/hs.httpserver.hsminweb.cgilua.urlcode.md)
		* [hsminweb](api/hs/hs.httpserver.hsminweb.md)
	* [image](api/hs/hs.image.md)
	* [inspect](api/hs/hs.inspect.md)
	* [ipc](api/hs/hs.ipc.md)
	* [itunes](api/hs/hs.itunes.md)
	* [javascript](api/hs/hs.javascript.md)
	* [json](api/hs/hs.json.md)
	* [keycodes](api/hs/hs.keycodes.md)
	* [layout](api/hs/hs.layout.md)
	* [location](api/hs/hs.location.md)
		* [geocoder](api/hs/hs.location.geocoder.md)
	* [logger](api/hs/hs.logger.md)
	* [menubar](api/hs/hs.menubar.md)
	* [messages](api/hs/hs.messages.md)
	* [midi](api/hs/hs.midi.md)
	* [milight](api/hs/hs.milight.md)
	* [mjomatic](api/hs/hs.mjomatic.md)
	* [mouse](api/hs/hs.mouse.md)
	* [network](api/hs/hs.network.md)
		* [configuration](api/hs/hs.network.configuration.md)
		* [host](api/hs/hs.network.host.md)
		* [ping](api/hs/hs.network.ping.md)
			* [echoRequest](api/hs/hs.network.ping.echoRequest.md)
		* [reachability](api/hs/hs.network.reachability.md)
	* [noises](api/hs/hs.noises.md)
	* [notify](api/hs/hs.notify.md)
	* [osascript](api/hs/hs.osascript.md)
	* [pasteboard](api/hs/hs.pasteboard.md)
	* [pathwatcher](api/hs/hs.pathwatcher.md)
	* [plist](api/hs/hs.plist.md)
	* [redshift](api/hs/hs.redshift.md)
	* [screen](api/hs/hs.screen.md)
		* [watcher](api/hs/hs.screen.watcher.md)
	* [settings](api/hs/hs.settings.md)
	* [sharing](api/hs/hs.sharing.md)
	* [socket](api/hs/hs.socket.md)
		* [udp](api/hs/hs.socket.udp.md)
	* [sound](api/hs/hs.sound.md)
	* [spaces.watcher](api/hs/hs.spaces.watcher.md)
	* [speech](api/hs/hs.speech.md)
		* [listener](api/hs/hs.speech.listener.md)
	* [spoons](api/hs/hs.spoons.md)
	* [spotify](api/hs/hs.spotify.md)
	* [spotlight](api/hs/hs.spotlight.md)
		* [group](api/hs/hs.spotlight.group.md)
		* [item](api/hs/hs.spotlight.item.md)
	* [sqlite3](api/hs/hs.sqlite3.md)
	* [streamdeck](api/hs/hs.streamdeck.md)
	* [styledtext](api/hs/hs.styledtext.md)
	* [tabs](api/hs/hs.tabs.md)
	* [task](api/hs/hs.task.md)
	* [timer](api/hs/hs.timer.md)
		* [delayed](api/hs/hs.timer.delayed.md)
	* [uielement](api/hs/hs.uielement.md)
		* [watcher](api/hs/hs.uielement.watcher.md)
	* [urlevent](api/hs/hs.urlevent.md)
	* [usb](api/hs/hs.usb.md)
		* [watcher](api/hs/hs.usb.watcher.md)
	* [utf8](api/hs/hs.utf8.md)
	* [vox](api/hs/hs.vox.md)
	* [watchable](api/hs/hs.watchable.md)
	* [webview](api/hs/hs.webview.md)
		* [datastore](api/hs/hs.webview.datastore.md)
		* [toolbar](api/hs/hs.webview.toolbar.md)
		* [usercontent](api/hs/hs.webview.usercontent.md)
	* [wifi](api/hs/hs.wifi.md)
		* [watcher](api/hs/hs.wifi.watcher.md)
	* [window](api/hs/hs.window.md)
		* [filter](api/hs/hs.window.filter.md)
		* [highlight](api/hs/hs.window.highlight.md)
		* [layout](api/hs/hs.window.layout.md)
		* [switcher](api/hs/hs.window.switcher.md)
		* [tiling](api/hs/hs.window.tiling.md)