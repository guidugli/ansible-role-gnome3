# Ansible Role: gnome3

Configure GNOME 3+ desktop and GDM settings on Linux systems.

## Badges

- CI: See `.github/workflows/CI.yml` in this repository.
- Galaxy: Publish metadata is driven by the role metadata and release workflow in this repository.

## Requirements

- A Linux host with GNOME version 3 or newer installed.
- `dconf` must be present for desktop and GDM settings to be rendered.
- Required collections:
  - `community.general >= 10.0.0`
  - `containers.podman >= 1.10.0`

## Variables

The role inputs are defined in `defaults/main.yml` and surfaced in `meta/argument_specs.yml`.
Common inputs include:

- `gnome_lock_settings` (type: `list`; default: `[org/gnome/Maps/checkin-foursquare-broadcast-twitter, org/gnome/Maps/checkin-foursquare-privacy, ...`)
- `gnome_background_color_shading_type` (type: `str`; default: `solid ...`)
- `gnome_background_show_desktop_icons` (type: `bool`; default: `true ...`)

For the complete authoritative defaults, review `defaults/main.yml` in this bundle.

## Example Playbook

> This role manages files under `/etc`, `/usr/share`, and `/etc/polkit-1`, so the playbook must provide privilege escalation externally.

```yaml
---
- name: Configure GNOME desktops
  hosts: workstations
  become: true
  roles:
    - role: guidugli.gnome3
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

## Execution Notes

### Privilege requirement

This role intentionally contains **no** `become` directives. The caller must provide `become: true` because these tasks write to privileged locations:

- Create and manage dconf database directories under /etc/dconf/db
- Render /etc/dconf/db/local.d/10-ansible and lock files under /etc/dconf/db/local.d/locks
- Render /etc/polkit-1/rules.d/40-default.rules when gnome_admin_group is defined
- Manage GDM profile and dconf files under /etc/dconf/profile and /etc/dconf/db/gdm.d
- Copy login logo content under /usr/share/pixmaps/logo
- Run dconf update (with umask 0022 preserved)

### Container / systemd behavior

The role can no-op on minimal containers that do not contain `gnome-session` or `dconf`. For reliable end-to-end validation of GDM-related behavior, prefer the template's `systemd` Molecule scenario because these areas are container-sensitive:

- GDM profile files under /etc/dconf/db/gdm.d and /etc/dconf/profile/gdm
- Interactive desktop settings that depend on gnome-session / dconf packages existing in the target image
- Tests that need a full graphical stack are better suited to the systemd-capable scenario copied from the template

## Notes on modernization

- Role-level `become` was removed to satisfy the privilege model.
- The `dconf update` handler keeps `umask 0022 && dconf update` unchanged so generated file permissions continue to match your expectation.
- Tagging was added to all modernized tasks and handlers using the `gnome3` prefix.
- The repository scaffold (`.github/`, `scripts/`, `ansible.cfg`, lint config, and Molecule scenario directories) was copied from the template bundle unchanged.
