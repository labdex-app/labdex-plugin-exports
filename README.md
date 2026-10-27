# File exports

A [labdex](https://github.com/reykimedev/labdex) plugin. Download generated files (OPNsense alias import, DNS zone, Ansible inventory, DHCP reservations, inventory YAML). Nothing is sent anywhere.

**Version** 1.1 · **Works with** labdex >=1.3,<2 · **Plugin id** `exports`

> [!WARNING]
> Built with AI, for home labs only: labdex and its plugins were written largely with an AI
> coding assistant (Claude), directed and reviewed by a human. They haven't had an independent
> security audit and may contain security problems. Run them on a trusted home network.

## Install

It ships with labdex: **Plugins › Marketplace**, then *Install* (nothing is downloaded). Updates arrive through the official Marketplace (signed with the labdex project key).

## Settings

| Setting | Notes |
| --- | --- |
| Ansible Vault password | Secrets in feature and host variables ({$secret: name}) become !vault values in the Ansible inventory; without a password they stay references |
| Vault id | Optional, e.g. labdex (written as $ANSIBLE_VAULT;1.2;AES256;labdex) |

## Actions

- **OPNsense aliases (JSON import)** (export)
- **DNS records (zone file)** (export)
- **DNS records (JSON)** (export)
- **Ansible inventory (YAML)** (export)
- **DHCP reservations (CSV)** (export)
- **Inventory (YAML)** (export)

## Releasing

Bump `version` in `plugin.yaml`, add a `## <version>` section to `CHANGELOG.md`, commit, then
publish a GitHub release tagged `v<version>` (web UI, or `gh release create v<version> --target main --notes ""`).
The release workflow signs the plugin with the `LABDEX_SIGNING_KEY` secret, attaches the zip and
`CHANGELOG.md` to the release and puts that version's CHANGELOG section into its description.
Files listed in `.releaseignore` stay out of the zip.
