# dotfiles
Dotfiles for setting up Lab PCs

# Contains
- PowerShell
- Windows Terminal
- `uv`/`ty`

# Useful infos

## `uv`/`ty`

The `.toml` and `.lock` file have been added for environment recovery, since the ones currently used are not versioned. To create the environment the following command was used:

```
# uv sync --prerelease=allow
```

in order to solve some issues with a dependency.
