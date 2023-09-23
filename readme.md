
Classic AltTab Helper
===================================

	Similarly to the built-in Alt-Tab feature in Windows,
	shows a menu that allows selecting windows to switch to.
	Replacement for task switching with Alt-Tab and Alt-Shift-Tab keys.

	Unlike modern Windows feature, shows only simple list
	as icons and text. It doesn't group windows of the same type
	or from the same process. The list is one-dimensional,
	which should make navigation fast and efficient.

	Use as an auxiliary task switching, rather than replacement,
	possible via command-line user configuration.


![preview_a](assets/preview_anim_01_outpv_7s.gif "preview_a")


Features
-----------------------

	* Can be started or disabled and turned off at any time.
	* Does not require to be run with the system startup.
	* Shows the tray icon that can be used to turn it off (can be disabled).
	* Does not require installation of any additional software, like service or driver.
	* Does not require - but is preferred - to be run with the administrator level priviledges,
	* Can be configured from the command line.


Installation
------------------------

	Required is a manual insallation. No setup or installer
	application provided at this point.


Manual Installation
------------------------

	Unpack  the archive to a directory of your choice.
	Run the executable file manually or add a shortcut
	to one of Windows' startup locations.

	Recomended location:
		"%UserProfile%\Start Menu\Programs\Startup"

	I.e. place shortcut to the executable in this folder to
	make Classic AltTab Helper start with the system.


Limitations
-----------------------

	If the program is not started with the administrator
	priviledges, it wont appear on the screen when tabbing out from
	windows that themself run in that priviledges, in turn.
	Note that this itself may be an intended functionality, instead.


FAQ
------------

	Q: How to close and disable this program?

	A1:
		Click on its icon in the tray area and close the window.
  	A2:
		Use mouse cursor to close the window.
	A3:
		While in the main window, press control key and then the 'Q' key.


Command Line Options
-------------------------

	Use following command line options to configure some parts
	of apperance or functionality.

	-color_spec TEXT

		Customizes apperance of colors used in the main window for the tabbing list.
		The text should consist of 5 colors as a semicolon separated list.
		Each of 5 colors, in turn, must specify 3 color components: red, green and blue.
		Example:
			-color_spec "128,128,128; 255,0,0; 255,255,0; 0,0,255; 0,99,0;"

	-bStartVisible 0|1  --  Default: 0

		If set to 1 shows, the main window with the list visible on
		startup. It will dissapear and continue to function normally
		on the first tabbing.

	-bTopmost 0|1  --  Default: 1

		Set to 0 to cause main window not set itself to the Top-Most
		window on the desktp. Not recommended to use. For test purposes.

	-bTrayIcon 0|1  --  Default: 1

		Set to 0 to disable the tray icon functionality.
		Tray icon can be used to easiliy show the main window,
		which in turn may be used to close and disable this tool.

	-nWinListOmitMode 0|7|10  --  Default: 10

		Mode to use. Ie. use 10 on Windows 10, and 7 on Windows 7.
		Setting this to 0 disables window omiting which will cause
		many, possibly unwamted, windows appear on the tabbing list.

	-bPrintWndNames2 0|1  --  Default: 0

		Debug purpose. Print all window names to the Stdout while tabbing.
		Requires Debug mode build.

	-bShowExeName 0|1  --  Default: 0

		Show executable name of the window in its item name in the tabbing list.

	-nMaxTitleLen INT  --  Default: 64

		Maximum length of the window text in the tabbing list.

	-anLabelSeparator STR  --  Default: "|"

		Separator text in the tabbing list. Changing is not recommended.

	-bUseSystemAltTab 1|0  --  Default: 1

		If set to 1, the default, replaces the system Alt+Tab keyboard shortcut
		with the one provided by this program - the main functionality.
		Only when this parameter is set to 0, setting different hotkeys
		than Alt-Tab is possible, and only then parameters -anHKAltTab
		and -anHKAltShiftTab are used.

	-anHKAltTab STR       --  Default: "8,192"
	-anHKAltShiftTab STR  --  Default: "12,192"

		Hotkey combinations that trigger the new switch-to-next and
		switch-to-previous actions, respectivelly; corresponding to
		the alt-tab and alt-shift-tab in the system.
		NOTE: this requires parameter -bUseSystemAltTab to be set to 0.

		By using this feature, the windows switching by the system
		is not replaced - the specified hotkeys will exist as auxiliary ones.

		STR must specify two values, separated with comma.
		First value spcifies the modkey combination, as OR-ed values,
		which can be on or more flags set.
		Values of 1,2,4 and 8 stand for Alt, Control, Shift and Winkey keys, respectivelly.
		Second value is the keyboard key code - the virtual key code from the Windows API documentation.
		Eg. 192 is the accent key (aka. tilde, aka. grave).
		-anHKAltTab is the one that simulates secondary Alt+Tab.
		-anHKAltShiftTab is the one that simulates secondary Alt+Shift+Tab.
		Either must not specify the key combinations that are already
		used by the system or other applications.

	-nToForeFixMs2 MILLISEC  --  Default: 320

		Additional check for improved tabbing functionality.
		Value is time in milliseconds. Recommended are values from 100-600.
		Use 0 to disable.


Changelog
------------------

	v1.2.1

		* Added more command line options.
		* Improvements for Windows 10.

	v1.3.1

		* Replacement for system Alt-Tab and Alt-Shift-Tab as default functionality.
		* More command line options.
		* Fixed bug with windows not activating from minimized state.
		* Fixed bug where maximized windows were incorrectly activating as "restored".


About
-----------------
	Author: ike9000
	URL:
		https://github.com/ike9000e/Classic-AltTab
