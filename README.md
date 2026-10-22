# AUTOM8TE-MD
𝐅𝐚𝐬𝐭𝐞𝐫 • 𝐑𝐞𝐥𝐢𝐚𝐛𝐥𝐞 • 𝐒𝐚𝐟𝐞

# AUTOM8TE MD Releases

This public repository holds release information only. It contains no bot code and no website code.

- `version.json` tells the system which version every bot should run.
- `CHANGELOG.md` lists what changed in each version.

## Version numbers

`MAJOR.MINOR.PATCH`

| Change | Example | Bump |
|---|---|---|
| New features | new commands | MINOR (1.0.0 to 1.1.0) |
| Bug fixes | corrected a command | PATCH (1.0.0 to 1.0.1) |
| Large or breaking changes | settings changed | MAJOR (1.0.0 to 2.0.0) |

## version.json

| Field | Meaning |
|---|---|
| `latest` | The version every app should run |
| `min` | Apps below this are shown as behind and should be updated soon |
| `ref` | The tag (or branch) of the private bot repository this version is built from |
| `released` | Release date |
| `notes` | Short lines shown to users when they send `.update` |

## How to publish a release

1. In the private bot repository, set `version` in `package.json`, commit, and create a tag, for example `v1.1.0`.
2. Edit `version.json` here: set `latest`, `ref` (the tag), `released` and `notes`. Raise `min` only for important fixes.
3. Add the entry to `CHANGELOG.md` and commit.

Within a minute the control server reads the new file. Then either:

- send `.update` from a bot, which updates that one bot, or
- use the admin dashboard, Updates, to update the available apps first and then all apps.

Pushing code to the private repository does not change running apps. Only a new `version.json` does.

## Rolling back

Put the previous version and tag back into `version.json` and run the update from the dashboard.

