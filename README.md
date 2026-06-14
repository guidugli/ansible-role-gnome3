[![CI](https://github.com/guidugli/ansible-role-gnome3/actions/workflows/CI.yml/badge.svg)](https://github.com/guidugli/ansible-role-gnome3/actions/workflows/CI.yml)
[![Release](https://github.com/guidugli/ansible-role-gnome3/actions/workflows/release.yml/badge.svg)](https://github.com/guidugli/ansible-role-gnome3/actions/workflows/release.yml)
[![Galaxy](https://img.shields.io/badge/Galaxy-guidugli.gnome3-blue)](https://galaxy.ansible.com/ui/standalone/roles/guidugli/gnome3/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

# Ansible Role: gnome3

Configure GNOME 3+ desktop and GDM settings on Linux systems.

## Requirements

- Ansible **2.14+**
- Python available on target hosts
- GNOME version 3 or newer installed
- `dconf` present on the target host for desktop and GDM settings
- Privilege escalation capable play for hosts where the role writes under `/etc`, `/usr/share`, or `/etc/polkit-1`
- Required collections:

```yaml
collections:
  - name: community.general
    version: ">=10.0.0"
  - name: containers.podman
    version: ">=1.10.0"
```

## Variables

All public inputs are defined in `defaults/main.yml` and surfaced through `meta/argument_specs.yml`.

### Core / lock and login controls

```yaml
gnome_lock_settings:
  - org/gnome/Maps/checkin-foursquare-broadcast-twitter
  - org/gnome/Maps/checkin-foursquare-privacy
  - org/gnome/Maps/checkin-facebook-privacy
  - org/gnome/Maps/checkin-foursquare-broadcast-facebook
  - org/gnome/desktop/file-sharing/require-password
  - org/gnome/online-accounts/whitelisted-providers
  - org/gnome/rhythmbox/sharing/enable-sharing
# gnome_admin_group: admin
# banner_graphical_msg: "Authorized uses only. All activity may be monitored and reported."
# banner_logo_file_name: greeter-logo.png
```

### Background / wallpaper

```yaml
# gnome_background_picture_uri: "file:///usr/share/backgrounds/gnome/libadwaita-l.jpg"
# gnome_background_picture_uri_dark: "file:///usr/share/backgrounds/gnome/libadwaita-d.jpg"
# gnome_background_picture_options: zoom
# gnome_background_picture_opacity: 100
# gnome_background_primary_color: "#3465a4"
# gnome_background_secondary_color: "#000000000000"
gnome_background_color_shading_type: solid
gnome_background_show_desktop_icons: true
```

### Weather / clocks / calendar / time

```yaml
# gnome_speed_unit: kph
# gnome_pressure_unit: atm
# gnome_distance_unit: km
# gnome_temperature_unit: centigrade
# gnome_weather_auto_location: false
# gnome_clock_geolocation: false
# gnome_show_weekdate: false
# gnome_automatic_timezone: false
```

### Session / calculator

```yaml
# gnome_auto_save_session: false
# gnome_logout_prompt: true
# gnome_session_idle_delay: 0
# gnome_calculator_source_currency: USD
# gnome_calculator_target_currency: BRL
# gnome_calculator_refresh_interval: 86400
# gnome_calculator_mode: advanced
```

### Desktop interface / fonts / shell / window manager

```yaml
# gnome_font_name: 'Cantarell 11'
# gnome_titlebar_uses_system_font: true
# gnome_titlebar_font: 'Cantarell Bold 11'
# gnome_action_middle_click_titlebar: none
# gnome_action_right_click_titlebar: menu
# gnome_action_double_click_titlebar: toggle-maximize
# gnome_toolbar_icon_size: large
# gnome_toolbar_detachable: false
# gnome_toolbar_style: both-horiz
# gnome_menubar_detachable: false
# gnome_menus_have_tearoff: false
# gnome_menubar_accel: 'F10'
# gnome_document_font_name: 'Cantarell 11'
# gnome_enable_hot_corners: true
# gnome_monospace_font_name: 'Source Code Pro 10'
# gnome_text_scaling_factor: '1.0'
# gnome_scaling_factor: 0
# gnome_cursor_size: 24
# gnome_cursor_blink: true
# gnome_cursor_blink_time: 1200
# gnome_cursor_blink_timeout: 10
# gnome_clock_show_weekday: false
# gnome_color_scheme: 'default'
# gnome_clock_show_date: true
# gnome_clock_show_seconds: false
# gnome_clock_format: '24h'
# gnome_enable_animations: true
# gnome_gtk_theme: Adwaita-dark
# gnome_cursor_theme: Adwaita
# gnome_icon_theme: Adwaita
# gnome_gtk_key_theme: Default
# gnome_overlay_scrolling: true
# gnome_gtk_enable_primary_paste: true
# gnome_locate_pointer: false
# gnome_show_battery_percentage: false
# gnome_button_layout: "appmenu:minimize,maximize,close"
# gnome_favorite_apps: "['firefox.desktop', 'org.gnome.Calendar.desktop', 'rhythmbox.desktop', 'virt-manager.desktop', 'org.gnome.Nautilus.desktop', 'org.gnome.Terminal.desktop', 'org.gnome.gedit.desktop']"
# gnome_shell_disable_user_extensions: false
# gnome_remember_mount_password: false
```

### Lockdown / media handling

```yaml
# gnome_mount_removable_storage_dev_as_read_only: false
# gnome_disable_command_line: false
# gnome_disable_logout: false
# gnome_disable_printing: false
# gnome_disable_lock_screen: false
# gnome_disable_print_setup: false
# gnome_disable_user_switching: false
# gnome_disable_application_handlers: false
# gnome_disable_save_to_disk: false
# gnome_disable_user_administration: false
# gnome_autorun_never: false
# gnome_automount_open: true
# gnome_automount: true
```

### Privacy / location / online accounts / locale

```yaml
# gnome_disable_microphone: false
# gnome_hide_identity: false
# gnome_recent_files_max_age: -1
# gnome_remove_old_tmp_files: false
# gnome_privacy_screen: false
# gnome_usb_protection_level: lockscreen
# gnome_disable_sound_output: false
# gnome_old_files_age: 30
# gnome_remember_app_usage: true
# gnome_disable_camera: false
# gnome_remember_recent_files: true
# gnome_report_technical_problems: false
# gnome_remove_old_trash_files: false
# gnome_show_full_name_top_bar: true
# gnome_send_software_usage_stats: false
# gnome_usb_protection: true
# gnome_enable_system_location: false
# gnome_location_max_accuracy_level: country
# gnome_online_accounts_whitelisted_providers: "['fedora', 'imap_smtp', 'owncloud']"
# gnome_locale_region: 'en_GB.UTF-8'
```

### Power / file chooser / Nautilus / sharing / maps

```yaml
# gnome_power_idle_dim: true
# gnome_power_sleep_inactive_battery_type: suspend
# gnome_power_sleep_inactive_battery_timeout: 1200
# gnome_power_idle_brightness: 30
# gnome_power_ambient_enabled: true
# gnome_power_sleep_inactive_ac_type: suspend
# gnome_power_sleep_inactive_ac_timeout: 0
# gnome_power_button_action: suspend
# gnome_default_folder_view: list-view
# gnome_sort_directories_first: true
# gnome_show_hidden_files: false
# gnome_file_sharing_ask_password: always
# gnome_maps_checkin_foursquare_broadcast_twitter: false
# gnome_maps_checkin_foursquare_privacy: private
# gnome_maps_checkin_facebook_privacy: SELF
# gnome_maps_checkin_foursquare_broadcast_facebook: false
```

### Screensaver / Rhythmbox / GNOME Software

```yaml
# gnome_screensaver_user_switch_enabled: true
# gnome_screensaver_show_full_name_in_top_bar: true
# gnome_screensaver_lock_enabled: true
# gnome_screensaver_lock_delay: 30
# gnome_screensaver_picture_uri: ''
# gnome_screensaver_picture_options: zoom
# gnome_screensaver_picture_opacity: 100
# gnome_screensaver_primary_color: '#3465a4'
# gnome_screensaver_secondary_color: '#000000000000'
# gnome_screensave_color_shading_type: solid
# gnome_rhythmbox_require_password: true
# gnome_rhythmbox_share_password: ''
# gnome_rhythmbox_enable_browsing: false
# gnome_rhythmbox_enable_sharing: false
# gnome_rhythmbox_share_name: ''
# gnome_rhythmbox_no_user_plugins: false
# gnome_rhythmbox_seen_plugins: "['rb', 'webremote', 'soundcloud', 'replaygain', 'pythonconsole', 'notification', 'mtpdevice', 'mpris', 'magnatune', 'lyrics', 'listenbrainz', 'ipod', 'im-status', 'grilo', 'fmradio', 'dbus-media-server', 'daap', 'cd-recorder', 'audioscrobbler', 'artsearch']"
# gnome_rhythmbox_active_plugins: "['rb', 'power-manager', 'notification', 'mtpdevice', 'mpris', 'mmkeys', 'iradio', 'ipod', 'generic-player', 'dbus-media-server', 'cd-recorder', 'audiocd', 'artsearch', 'android']"
# gnome_software_allow_updates: true
# gnome_software_download_updates: true
# gnome_software_download_updates_notify: true
```

### gedit and Text Editor

```yaml
# gnome_geditor_auto_save: true
# gnome_geditor_auto_save_interval: 10
# gnome_geditor_auto_indent: true
# gnome_geditor_tabs_size: 8
# gnome_geditor_insert_spaces: true
# gnome_geditor_use_default_font: true
# gnome_geditor_wrap_last_split_mode: word
# gnome_geditor_background_pattern: none
# gnome_geditor_smart_home_end: after
# gnome_geditor_search_highlighting: true
# gnome_geditor_scheme: tango
# gnome_geditor_editor_font: 'Monospace 12'
# gnome_geditor_bracket_matching: true
# gnome_geditor_syntax_highlighting: true
# gnome_geditor_display_right_margin: false
# gnome_geditor_max_undo_actions: 2000
# gnome_geditor_restore_cursor_position: true
# gnome_geditor_highlight_current_line: false
# gnome_geditor_display_line_numbers: true
# gnome_geditor_wrap_mode: word
# gnome_geditor_ensure_trailing_newline: true
# gnome_geditor_right_margin_position: 80
# gnome_geditor_create_backup_copy: false
# gnome_texteditor_auto_indent: true
# gnome_texteditor_auto_save_delay: 10
# gnome_texteditor_editor_font: 'Monospace 11'
# gnome_texteditor_discover_settings: true
# gnome_texteditor_draw_spaces: '@as []'
# gnome_texteditor_enable_snippets: false
# gnome_texteditor_highlight_current_line: false
# gnome_texteditor_indent_style: 'tab'
# gnome_texteditor_indent_width: -1
# gnome_texteditor_keybindings: 'default'
# gnome_texteditor_line_height: 1.2
# gnome_texteditor_highlight_recolor_window: true
# gnome_texteditor_highlight_restore_session: true
# gnome_texteditor_right_margin_position: 120
# gnome_texteditor_show_grid: false
# gnome_texteditor_show_line_numbers: false
# gnome_texteditor_show_map: false
# gnome_texteditor_show_right_margin: false
# gnome_texteditor_spellcheck: true
# gnome_texteditor_style_scheme: 'Adwaita'
# gnome_texteditor_style_variant: 'dark'
# gnome_texteditor_tab_width: 8
# gnome_geditor_use_system_font: true
# gnome_texteditor_wrap_text: true
# gnome_ibus_emoji_hotkey: "@as ['period']"
```

## Example Playbook

### Minimal example

```yaml
- name: Configure GNOME desktops
  hosts: workstations
  become: true
  roles:
    - role: guidugli.gnome3
```

### Login banner and logo

```yaml
- name: Configure login screen branding
  hosts: workstations
  become: true
  roles:
    - role: guidugli.gnome3
      vars:
        banner_graphical_msg: "Authorized uses only. All activity may be monitored and reported."
        banner_logo_file_name: greeter-logo.png
```

### Lock selected settings and harden privacy

```yaml
- name: Lock selected GNOME settings
  hosts: workstations
  become: true
  roles:
    - role: guidugli.gnome3
      vars:
        gnome_lock_settings:
          - org/gnome/desktop/file-sharing/require-password
          - org/gnome/rhythmbox/sharing/enable-sharing
        gnome_disable_camera: true
        gnome_disable_microphone: true
        gnome_usb_protection: true
        gnome_usb_protection_level: lockscreen
```

## Molecule Testing Instructions

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements-dev.txt
ansible-galaxy collection install -r requirements.yml
molecule test -s default
molecule test -s systemd
```

A convenience script is also present:

```bash
./scripts/run_local.sh
```

## Execution Notes

### Privilege requirements

This role intentionally contains no `become` directives. Callers must provide elevated privileges when applying the role to normal hosts because the role writes under `/etc/dconf/db`, `/etc/dconf/profile`, `/etc/polkit-1/rules.d`, and `/usr/share/pixmaps/logo`, and it runs `dconf update` through a handler.

### Container / systemd behavior

The role can no-op on minimal containers that do not include `gnome-session` or `dconf`. For reliable validation of GDM-related behavior and other systemd-sensitive paths, use the `systemd` Molecule scenario. GDM profile files under `/etc/dconf/db/gdm.d` and `/etc/dconf/profile/gdm` are explicitly called out as container-sensitive areas.

## Features

- Detects the installed GNOME session version from package facts and selects the matching dconf template.
- Renders a system-wide desktop profile under `/etc/dconf/db/local.d/10-ansible`.
- Renders a lock file under `/etc/dconf/db/local.d/locks/00-ansible-lock`.
- Optionally renders polkit admin rules when `gnome_admin_group` is set.
- Optionally manages GDM login banner text and logo.
- Refreshes the dconf database through a handler instead of forcing repeated command execution.
- Includes both `default` and `systemd` Molecule scenarios.

## Supported platforms

The role metadata lists Fedora, Ubuntu, and Debian. The bundled Molecule inventory and shared matrix include Ubuntu 26.04 and 24.04, Debian 13 and 12, and Fedora 44 and 43.

## Built-in behavior / important files

### Desktop dconf behavior

The role manages:

- `/etc/dconf/db/local.d/10-ansible`
- `/etc/dconf/db/local.d/locks/00-ansible-lock`
- the GNOME template selected from `templates/10-ansible-gnome*`

### GDM behavior

When banner or logo settings are defined, the role can manage:

- `/etc/dconf/profile/gdm`
- `/etc/dconf/db/gdm.d/01-logo`
- `/etc/dconf/db/gdm.d/01-banner-message`
- `/usr/share/pixmaps/logo/<file>`

### Policy behavior

When `gnome_admin_group` is set, the role manages:

- `/etc/polkit-1/rules.d/40-default.rules`

## How it works

1. `ansible.builtin.package_facts` gathers installed package data.
2. The role derives `gnome_version` from the installed `gnome-session` package.
3. It validates that the detected version is in the supported template list.
4. It ensures the role-managed dconf directories exist.
5. It renders desktop dconf settings and the lock file.
6. It optionally includes `tasks/gdm.yml` when GNOME and `dconf` are present.
7. It optionally renders polkit rules when `gnome_admin_group` is defined.
8. The `Refresh dconf database` handler runs `umask 0022 && dconf update`.

## Design notes

### Privilege escalation / become

Role-managed files do not set `become`; external execution context is responsible for privilege escalation. The example playbooks therefore use `become: true` for normal host execution.

### Idempotency

Templates, file resources, and `community.general.ini_file` are used for the main configuration surfaces. The `dconf update` handler is marked `changed_when: false`, which keeps the handler from reporting a change on every run.

### Container compatibility

The role uses package facts and conditional checks around `gnome-session` and `dconf`, which lets constrained test containers skip desktop-specific rendering when the relevant packages are absent. The systemd Molecule scenario is still the preferred path for end-to-end GDM validation.

## Release workflow

Generated repository metadata is refreshed through the shared generator scripts:

```bash
./scripts/update_release_metadata.sh
./scripts/release.sh --version v1.2.0 --message "Release v1.2.0"
```

## Repository structure

```text
defaults/
  main.yml
handlers/
  main.yml
meta/
  argument_specs.yml
  main.yml
molecule/
  shared/
  default/
  systemd/
scripts/
  render_inventory.py
  render_meta_main.py
  update_matrix.py
  update_release_metadata.sh
  release.sh
  run_local.sh
tasks/
  main.yml
  gdm.yml
templates/
  00-ansible-lock
  10-ansible-gnome3
  10-ansible-gnome40
  40-default.rules.j2
```

## License

MIT

## Author

Carlos Guidugli
