Ansible Role: gnome3
=========

A brief description of the role goes here.

Requirements
------------

System running Gnome version 3 or newer.

Role Variables
--------------

**Available variables are listed below, along with default values (see defaults/main.yml):**

    gnome_lock_settings:
      - org/gnome/Maps/checkin-foursquare-broadcast-twitter
      - org/gnome/Maps/checkin-foursquare-privacy
      - org/gnome/Maps/checkin-facebook-privacy
      - org/gnome/Maps/checkin-foursquare-broadcast-facebook
      - org/gnome/desktop/file-sharing/require-password
      - org/gnome/online-accounts/whitelisted-providers
      - org/gnome/rhythmbox/sharing/enable-sharing

    banner_graphical_msg: "Authorized uses only. All activity may be monitored and reported."

Message to be displayed on login screen

    banner_logo_file_name: greeter-logo.png

Copy file from files directory to /usr/share/pixmaps/logo and set GDM dconf profile to use it

    gnome_background_picture_uri: "file:///usr/share/backgrounds/fedora-workstation/aurora-over-iceland.png"

URI to use for the background image. Note that the backend only supports local (file://) URIs.

    gnome_background_picture_options: zoom

Determines how the image set by wallpaper_filename is rendered. Possible values are “none”, “wallpaper”, “centered”, “scaled”, “stretched”, “zoom”, “spanned”.

    gnome_background_picture_opacity: 100

Opacity with which to draw the background picture.

    gnome_background_primary_color: "#000000000000"

Left or Top color when drawing gradients, or the solid color.

    gnome_background_secondary_color: "#000000000000"

Right or Bottom color when drawing gradients, not used for solid color.

    gnome_background_color_shading_type: solid

How to shade the background color. Possible values are “horizontal”, “vertical”, and “solid”.

    gnome_background_show_desktop_icons: yes
  
If set to true, then file manager will draw the icons on the desktop.

    gnome_speed_unit: kph

The unit of speed used for showing weather (for example for wind speed). Valid values are “ms” (meters per second), “kph” (kilometers per hour), “mph” (miles per hour), “knots” and “bft” (Beaufort scale).

    gnome_pressure_unit: atm

The unit of pressure used for showing weather. Valid values are “kpa” (kilopascal), “hpa” (hectopascal), “mb” (millibar, mathematically equivalent to 1 hPa but shown differently), “mm-hg” (millimeters of mercury), “inch-hg” (inches of mercury), “atm” (atmospheres).

    gnome_distance_unit: km

The unit of distance used for showing weather (for example for visibility or for distance of important events). Valid values are “meters”, “km” and “miles”.

    gnome_temperature_unit: centigrade

The unit of temperature used for showing weather. Valid values are “kelvin”, “centigrade” and “fahrenheit”.

    gnome_weather_auto_location: no

Decides whether to fetch current location or not.

    gnome_auto_save_session: no

If enabled, gnome-session will save the session automatically.

    gnome_logout_prompt: yes

If enabled, gnome-session will prompt the user before ending a session.

    gnome_session_idle_delay: 0

The number of seconds of inactivity before the session is considered idle.

    gnome_calculator_source_currency: USD
    gnome_calculator_target_currency: BRL

Currencies to convert from to

    gnome_calculator_refresh_interval: 86400

How often the currency exchange rates should be updated
Valid values are 604800 (weekly) and 86400 (daily)

    gnome_calculator_mode: advanced

Calculator mode: basic, advanced, financial, programming, keyboard

    gnome_clock_geolocation: no

Turn geolocation support on and off.

    gnome_show_weekdate: false

If true, display the ISO week date in the calendar.

    gnome_automatic_timezone: no

Whether to automatically update the timezone using geolocation.

    gnome_font_name: 'Cantarell 11'

Name of the default font used by gtk+

    gnome_titlebar_uses_system_font: yes

If true, ignore the titlebar-font option, and use the standard application font for window titles.

    gnome_titlebar_font: 'Cantarell Bold 11'

A font description string describing a font for window titlebars. The size from the description will only be used if the titlebar-font-size option is set to 0. Also, this option is disabled if the titlebar-uses-desktop-font option is set to true.

    gnome_action_middle_click_titlebar: none

This option determines the effects of middle-clicking on the title bar.
Current valid options are “toggle-shade”, which will shade/unshade the window, “toggle-maximize” which will maximize/unmaximize the window, “toggle-maximize-horizontally” and “toggle-maximize-vertically” which will maximize/unmaximize the window in that direction only, “minimize” which will minimize the window, “shade” which will roll the window up, “menu” which will display the window menu, “lower” which will put the window behind all the others, and “none” which will not do anything

    gnome_action_right_click_titlebar: menu

This option determines the effects of right-clicking on the title bar. same options as gnome_action_middle_click_titlebar

    gnome_action_double_click_titlebar: toggle-maximize

This option determines the effects of double-clicking on the title bar.
same options as gnome_action_middle_click_titlebar

    gnome_toolbar_icon_size: large

Size of icons in toolbars, either “small” or “large”.

    gnome_toolbar_detachable: no

Whether the user can detach toolbars and move them around

    gnome_toolbar_style: both-horiz

Toolbar style. Valid values are "both", "both-horiz", "icons" and "text"

    gnome_menubar_detachable: no

Whether the user can detach menubars and move them around

    gnome_menus_have_tearoff: no

Whether menus should have a tearoff

    gnome_menubar_accel: 'F10'

Keyboard shortcut to open the menu bars

    gnome_document_font_name: 'Cantarell 11'

Name of the default font used for reading documents

    gnome_enable_hot_corners: yes

If true, the activities overview can be accessed by moving the mouse to the top-left corner.

    gnome_monospace_font_name: "Source Code Pro 10"

Name of a monospaced (fixed-width) font for use in locations like terminals.

    gnome_text_scaling_factor: '1.0'

Factor used to enlarge or reduce text display, without changing font size.

    gnome_scaling_factor: 0

Integer factor used to scale windows by. For use on high-dpi screens.
0 means pick automatically based on monitor.

    gnome_cursor_size: 24

Size of the cursor used as cursor theme.

    gnome_cursor_blink: yes

Whether the cursor should blink.

    gnome_cursor_blink_time: 1200

Length of the cursor blink cycle, in milliseconds.

    gnome_cursor_blink_timeout: 10

Time after which the cursor stops blinking, in seconds.

    gnome_clock_show_weekday: no

If true, display weekday in the clock, in addition to time.

    gnome_clock_show_date: yes

If true, display date in the clock, in addition to time.

    gnome_clock_show_seconds: no

If true, display seconds in the clock.

    gnome_clock_format: '24h'

Whether the clock displays in 24h or 12h format

    gnome_enable_animations: yes

Whether animations should be displayed. Note: this is a global key, it changes the behaviour of the window manager, the panel, etc.

    gnome_gtk_theme: Adwaita-dark

Basename of the default theme used by gtk+.
Other possible values: Adwaita, HighContrast, HighContrastInverse

    gnome_cursor_theme: Adwaita

Cursor theme name. Used only by Xservers that support the Xcursor extension.

    gnome_icon_theme: Adwaita

Icon theme to use for the panel, nautilus etc.
Other possible values: gnome, hicolor, HighContrast

    gnome_gtk_key_theme: Default

Basename of the default keybinding theme used by gtk+.

    gnome_overlay_scrolling: yes

Whether scrollbars should be overlayed as indicators. Depending on input devices in use, permanent scrollbars may still be displayed.

    gnome_gtk_enable_primary_paste: yes

If true, gtk+ uses the primary paste selection, usually triggered by a middle mouse button click.

    gnome_locate_pointer: no

If true, pressing a key will highlight the current pointer location on screen

    gnome_show_battery_percentage: no

If true, display battery percentage in the status menu, in addition to the icon.

    gnome_button_layout: "appmenu:minimize,maximize,close"

Arrangement of buttons on the titlebar. The value should be a string, such as “menu:minimize,maximize,spacer,close”; the colon separates the left corner of the window from the right corner, and the button names are comma-separated. Duplicate buttons are not allowed. Unknown button names are silently ignored so that buttons can be added in future metacity versions without breaking older versions. A special spacer tag can be used to insert some space between two adjacent buttons.

    gnome_mount_removable_storage_dev_as_read_only: no

Prevent users from writing or modifying files on removable storage devices (i.e. flash disks, mobile phones, cameras).

    gnome_disable_command_line: no

Prevent the user from accessing the terminal or specifying a command line to be executed. For example, this would disable access to the panel’s “Run Application” dialog.

    gnome_disable_logout: no

Prevent the user from logging out.

    gnome_disable_printing: no

Prevent the user from printing. For example, this would disable access to all applications’ “Print” dialogs.

    gnome_disable_lock_screen: no

Prevent the user to lock his screen.

    gnome_disable_print_setup: no

Prevent the user from modifying print settings. For example, this would disable access to all applications’ “Print Setup” dialogs.

    gnome_disable_user_switching: no

Prevent the user from switching to another account while his session is active.

    gnome_disable_application_handlers: no

Prevent running any URL or MIME type handler applications.

    gnome_disable_save_to_disk: no

Prevent the user from saving files to disk. For example, this would disable access to all applications’ “Save as” dialogs.

    gnome_disable_user_administration: no

Stop the user from modifying user accounts. By default, we allow adding and removing users, as well as changing other users settings.

    gnome_favorite_apps: "['firefox.desktop', 'org.gnome.Calendar.desktop', 'rhythmbox.desktop',
                          'virt-manager.desktop', 'org.gnome.Nautilus.desktop', 'org.gnome.Terminal.desktop',
                          'org.gnome.gedit.desktop']"

The applications corresponding to these identifiers will be displayed in the favorites area.

    gnome_shell_disable_user_extensions: no

Disable all extensions the user has enabled without affecting the “enabled-extension” setting.

    gnome_remember_mount_password: no

The shell will request a password when an encrypted device or a remote filesystem is mounted. If the password can be saved for future use a “Remember Password” checkbox will be present. This key sets the default state of the checkbox.

    gnome_autorun_never: no

If set to true, then Nautilus will never prompt nor autorun/autostart programs when a medium is inserted.

    gnome_automount_open: yes

If set to true, then Nautilus will automatically open a folder when media is automounted. This only applies to media where no known x-content/* type was detected; for media where a known x-content type is detected, the user configurable action will be taken instead.

    gnome_automount: yes

If set to true, then Nautilus will automatically mount media such as user-visible hard disks and removable media on start-up and media insertion.

    gnome_disable_microphone: no

If TRUE, applications should not use the microphone.

    gnome_hide_identity: no

If set to true, the system will make an effort to not divulge the user’s identity on screen or on the network.

    gnome_recent_files_max_age: -1

Recently used files will be remembered for this many days. If set to 0, recent files will not be remembered; if set to -1, they will be retained indefinitely.

    gnome_remove_old_tmp_files: no

If TRUE, automatically remove temporary files when they are older than “old-files-age” days.

    gnome_usb_protection_level: lockscreen

If set to “lockscreen”, only when the lock screen is present new USB devices will be rejected; if set to “always”, all new USB devices will always be rejected.

    gnome_disable_sound_output: no

If TRUE, applications should not make sound.

    gnome_old_files_age: 30

Consider trash and temporary files old after this many days.

    gnome_remember_app_usage: yes

If FALSE, application usage will not be monitored and recorded.

    gnome_disable_camera: no

If TRUE, applications should not use the camera.

    gnome_remember_recent_files: yes

If FALSE, applications will not remember recently used files.

    gnome_report_technical_problems: no

If TRUE, anonymized reports will be sent automatically to the vendor.

    gnome_remove_old_trash_files: no

If TRUE, automatically remove files from the trash when they are older than “old-files-age” days.

    gnome_show_full_name_top_bar: yes

Whether the users full name is shown in the user menu or not.

    gnome_send_software_usage_stats: no

If FALSE, no anonymous installation or removal information will be sent to the vendor.

    gnome_usb_protection: yes

If the USBGuard service is present and this setting is enabled, USB devices will be protected as configured in the usb-protection-level setting.

    gnome_enable_system_location: no

If true, applications are allowed to access location information.

    gnome_location_max_accuracy_level: country

Configures the maximum level of location accuracy applications are allowed to see.
Valid options are “country”, “city”, “neighborhood”, “street”, and “exact” (typically requires GPS receiver). Please keep in mind that this only controls what GeoClue will allow applications to see and they can find user’s location on their own using network resources (albeit with street-level accuracy at best).

    gnome_online_accounts_whitelisted_providers: "['fedora', 'imap_smtp', 'owncloud']"

A list of strings representing the providers that are allowed to be loaded (default: 'all'). This is only evaluated on startup. THIS IS A STRING VARIABLE

gnome_locale_region: "en_GB.UTF-8"

Specify the locale to be used for displaying dates, times and numbers formats.

    gnome_power_idle_dim: yes

If the screen should be dimmed to save power when the computer is idle.

    gnome_power_sleep_inactive_battery_type: suspend

The type of sleeping that should be performed when the computer is inactive.

    gnome_power_sleep_inactive_battery_timeout: 1200

The amount of time in seconds the computer on battery power needs to be inactive before it goes to sleep.
A value of 0 means never.

    gnome_power_idle_brightness: 30

This is the laptop panel screen brightness used when the session is idle.

    gnome_power_ambient_enabled: yes

If the ambient light sensor functionality is enabled.

    gnome_power_sleep_inactive_ac_type: suspend

The type of sleeping that should be performed when the computer is inactive.

    gnome_power_sleep_inactive_ac_timeout: 0

The amount of time in seconds the computer on AC power needs to be inactive before it goes to sleep.
A value of 0 means never.

    gnome_power_button_action: suspend

The action to take when the system power button is pressed. This action is hard-coded (and the setting ignored) on virtual machines (power off) and tablets (suspend).

    gnome_default_folder_view: list-view

When a folder is visited this viewer is used unless you have selected another view for that particular folder.
Possible values are “list-view”, and “icon-view”.

    gnome_sort_directories_first: yes

If set to true, then folders are shown before files in the list.

    gnome_show_hidden_files: no

Controls whether to show hidden files or not.

    gnome_file_sharing_ask_password: always

When to ask for passwords. Possible values are "never", "on_write", and "always".

    gnome_maps_checkin_foursquare_broadcast_twitter: no

Indicates if Foursquare should broadcast the check-in as a tweet in the Twitter account associated with the Foursquare account.

    gnome_maps_checkin_foursquare_privacy: private

Latest used Foursquare check-in privacy setting. Possible values are: public, followers or private.

    gnome_maps_checkin_facebook_privacy: SELF

Latest used Facebook check-in privacy setting. Possible values are: EVERYONE, FRIENDS_OF_FRIENDS, ALL_FRIENDS or SELF.

    gnome_maps_checkin_foursquare_broadcast_facebook: no

Indicates if Foursquare should broadcast the check-in as a post in the Facebook account associated with the Foursquare account.

    gnome_screensaver_user_switch_enabled: yes

Set this to TRUE to offer an option in the unlock dialog to switch to a different user account.

    gnome_screensaver_show_full_name_in_top_bar: yes

Whether the user’s full name is shown in the lock screen or not. This only affects the screen shield, the name is always shown in the unlock dialog.

    gnome_screensaver_lock_enabled: yes

Set this to TRUE to lock the screen when the screensaver goes active.

    gnome_screensaver_lock_delay: 30

The number of seconds after screensaver activation before locking the screen.

    gnome_screensaver_picture_uri: ""

URI to use for the background image. Note that the backend only supports local (file://) URIs.

    gnome_screensaver_picture_options: zoom

Determines how the image set by wallpaper_filename is rendered. Possible values are “none”, “wallpaper”, “centered”, “scaled”, “stretched”, “zoom”, “spanned”.

    gnome_screensaver_picture_opacity: 100

Opacity with which to draw the background picture.

    gnome_screensaver_primary_color: "#000000000000"

Left or Top color when drawing gradients, or the solid color.

    gnome_screensaver_secondary_color: "#000000000000"

Right or Bottom color when drawing gradients, not used for solid color.

    gnome_screensave_color_shading_type: solid

How to shade the background color. Possible values are “horizontal”, “vertical”, and “solid”.

    gnome_rhythmbox_require_password: yes

When enabled, Rhythmbox will require a password for others to access your music over the network.

    gnome_rhythmbox_share_password: "{{ lookup('password', '/tmp/passwordfile chars=ascii_letters,digits,hexdigits,punctuation length=16') }}"

Password that is required for accessing your shared music.

    gnome_rhythmbox_enable_browsing: no

When enabled, Rhythmbox will search for shared music on your local network

    gnome_rhythmbox_enable_sharing: no

When enabled, Rhythmbox will share your music with other computers

    gnome_rhythmbox_share_name: ""

Name other computers will see your music shared as

    gnome_rhythmbox_no_user_plugins: no

When set prevents loading of plugins from the user's home directory

    gnome_rhythmbox_seen_plugins: "['rb', 'webremote', 'soundcloud', 'replaygain', 'pythonconsole', 'notification',
                                    'mtpdevice', 'mpris', 'magnatune', 'lyrics', 'listenbrainz', 'ipod', 'im-status',
                                    'grilo', 'fmradio', 'dbus-media-server', 'daap', 'cd-recorder', 'audioscrobbler',
                                    'artsearch']"

List of plugins that have previously been seen.
Previously unseen plugins may be automatically enabled.

    gnome_rhythmbox_active_plugins: "['rb', 'power-manager', 'notification', 'mtpdevice', 'mpris', 'mmkeys', 'iradio',
                                      'ipod', 'generic-player', 'dbus-media-server', 'cd-recorder', 'audiocd',
                                      'artsearch', 'android']"

List of active plugin names. These plugins will be loaded on startup if available.
This variable is a string variable, not an ansible list

    gnome_software_allow_updates: yes

If disabled, GNOME Software will hide the updates panel, not perform any automatic updates actions or prompt for upgrades.

    gnome_software_download_updates: yes

If enabled, GNOME Software automatically downloads software updates in the background, also installing ones that do not require a reboot.

    gnome_software_download_updates_notify: yes

If enabled, GNOME Software notifies the user about updates that happened whilst the user was idle.

    gnome_geditor_auto_save: true

Whether gedit should automatically save modified files after a time interval.
You can set the time interval with the “Autosave Interval” option.

    gnome_geditor_auto_save_interval: 10

Number of minutes after which gedit will automatically save modified files. This will only take effect if the “Autosave” option is turned on.

    gnome_geditor_auto_indent: true

Whether gedit should enable automatic indentation.

    gnome_geditor_tabs_size: 8

Specifies the number of spaces that should be displayed instead of Tab characters.

    gnome_geditor_insert_spaces: true

Whether gedit should insert spaces instead of tabs.

    gnome_geditor_use_default_font: true

Whether to use the system’s default fixed width font for editing text instead of a font specific to gedit. If this option is turned off, then the font named in the “Editor Font” option will be used instead of the system font.

    gnome_geditor_wrap_last_split_mode: word

Specifies the last split mode used with line wrapping mode, so that when wrapping mode is off we still remember the split mode choice. Use “word” for wrapping at word boundaries, and “char” for wrapping at individual character boundaries.

    gnome_geditor_background_pattern: none

Whether the document will get a background pattern painted.

    gnome_geditor_smart_home_end: after

Specifies how the cursor moves when the HOME and END keys are pressed. Use “disabled” to always move at the start/end of the line, “after” to move to the start/end of the line the first time the keys are pressed and to the start/end of the text ignoring whitespaces the second time the keys are pressed, “before” to move to the start/end of the text before moving to the start/end of the line and “always” to always move to the start/end of the text instead of the start/end of the line.

    gnome_geditor_search_highlighting: true

Whether gedit should highlight all the occurrences of the searched text.

    gnome_geditor_scheme: tango

The ID of a GtkSourceView Style Scheme used to color the text.

    gnome_geditor_editor_font: 'Monospace 12'

A custom font that will be used for the editing area. This will only take effect if the “Use Default Font” option is turned off.

    gnome_geditor_bracket_matching: true

Whether gedit should highlight matching brackets.

    gnome_geditor_syntax_highlighting: true

Whether gedit should enable syntax highlighting.

    gnome_geditor_display_right_margin: false

Whether gedit should display the right margin in the editing area.

    gnome_geditor_max_undo_actions: 2000

Maximum number of actions that gedit will be able to undo or redo. Use “-1” for unlimited number of actions.

    gnome_geditor_restore_cursor_position: true

Whether gedit should restore the previous cursor position when a file is loaded.

    gnome_geditor_highlight_current_line: false

Whether gedit should highlight the current line.

    gnome_geditor_display_line_numbers: true

Whether gedit should display line numbers in the editing area.

    gnome_geditor_wrap_mode: word

Specifies how to wrap long lines in the editing area. Use “none” for no wrapping, “word” for wrapping at word boundaries, and “char” for wrapping at individual character boundaries. Note that the values are case-sensitive, so make sure they appear exactly as mentioned here.

    gnome_geditor_ensure_trailing_newline: true

Whether gedit will ensure that documents always end with a trailing newline.

    gnome_geditor_right_margin_position: 80

Specifies the position of the right margin.

    gnome_geditor_create_backup_copy: false

Whether gedit should create backup copies for the files it saves.

    gnome_ibus_emoji_hotkey: "[]"

Hotkey to add emojis. Default Control+Shift+e may interfere with Terminator.


Dependencies
------------

No dependencies.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: guidugli.gnome3 }

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2020 by Carlos Guidugli.
