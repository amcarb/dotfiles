# dotfiles
Dotfiles for setting up Lab PCs

# Contains
- PowerShell
- Windows Terminal
- `uv`/`ty`

# Useful infos

`winget` install:
- `winget install --id Microsoft.PowerShell --installer-type wix`
- `winget install JanDeDobbeleer.OhMyPosh --source winget`
- `oh-my-posh font install meslo`
- `winget install --id Microsoft.PowerToys --source winget`

## Powershell

Place the `PowerShell` folder in the path  `C:\Users\usr\Documents\PowerShell`.

## `uv`/`ty`

The `.toml` and `.lock` file have been added for environment recovery, since the ones currently used are not versioned. To create the environment the following command was used:

```
# uv sync --prerelease=allow
```

in order to solve some issues with a dependency.
