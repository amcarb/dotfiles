# Workspace guide

## Where to look for context
For general questions (when I don't name a specific file, function or instrument),
build your context from these paths **first**, in this order. Only search elsewhere
if the answer isn't there, and tell me when you did.

| Path | Import name | What it contains | Use it for |
|---|---|---|---|
| `NQCP-Phot-Git-Protocols/` | `photonic_protocols` | Measurement protocols i.e. Jupyter notebooks | the code actually used for measurements |
| `NQCP-Phot-Git-Controllers/` | `controllers` | Controllers used to control the instruments | Python classes for controlling at least one instrument at a time |
| `NQCP-Phot-Git-Instruments/` | `instruments` | Instruments used in the lab | Python classes for interfacing Controllers and Drivers |
| `NQCP-Phot-Git-Drivers/` | `photonicdrivers` | Device drivers | Device APIs, connecting to hardware |
| `NQCP-Phot-Git-Analysis/` | `analysis` | Analysis scripts | Python classes for analyzing data |
| `NQCP-Phot-Git-LabServer/` | `labserver` | Lab server and data management | the server that runs the lab, allowing Protocols to execute drivers from any lab pc |

Layering: Protocols → Controllers → Instruments → Drivers (each layer imports the one below;
Protocols also import every layer directly). LabServer exposes Drivers/Instruments remotely,
so Protocols can use hardware attached to another lab pc.

## Skip unless I ask
- `NQCP.wiki` - the lab wiki, for human-readable documentation
- Generated/environment files: `.venv/`, `*.egg-info/`, `uv.lock`, `__pycache__/`

## Specific questions
If I name a file, function, class or instrument, go straight to it.
The list above doesn't apply.

## Shared environment
- `C:\gitRepositories` is one uv workspace: the root `pyproject.toml` lists every
  `NQCP-Phot-Git-*` repo as a member (except Simulations) and there is a single root `.venv`.
  Run `uv sync` from the root, not inside a repo.
- Optional extras: `attocube`, `upload` (needs the private Azure feed).
  A base `uv sync` works without either.
- `sync_uv_files.ps1 --pull | --push` copies `pyproject.toml`, `uv.lock` and `ty.toml` between
  the root and `NQCP-Phot-Git-GrafanaLogging\grafanaLogger\uv`. It overwrites files, so don't run it
  unless I ask.

## Conventions
- uv, `Python 3.13`, tests with `pytest`
# Workspace guide

## Where to look for context
For general questions (when I don't name a specific file, function or instrument),
build your context from these paths **first**, in this order. Only search elsewhere
if the answer isn't there, and tell me when you did.

| Path | Import name | What it contains | Use it for |
|---|---|---|---|
| `NQCP-Phot-Git-Protocols/` | `photonic_protocols` | Measurement protocols i.e. Jupyter notebooks | the code actually used for measurements |
| `NQCP-Phot-Git-Controllers/` | `controllers` | Controllers used to control the instruments | Python classes for controlling at least one instrument at a time |
| `NQCP-Phot-Git-Instruments/` | `instruments` | Instruments used in the lab | Python classes for interfacing Controllers and Drivers |
| `NQCP-Phot-Git-Drivers/` | `photonicdrivers` | Device drivers | Device APIs, connecting to hardware |
| `NQCP-Phot-Git-LabServer/` | `labserver` | Lab server and data management | the server that runs the lab, allowing Protocols to execute drivers from any lab pc |

Layering: Protocols → Controllers → Instruments → Drivers (each layer imports the one below;
Protocols also import every layer directly). LabServer exposes Drivers/Instruments remotely,
so Protocols can use hardware attached to another lab pc.

## Skip unless I ask
- `NQCP.wiki` - the lab wiki, for human-readable documentation
- Generated/environment files: `.venv/`, `*.egg-info/`, `uv.lock`, `__pycache__/`

## Specific questions
If I name a file, function, class or instrument, go straight to it.
The list above doesn't apply.

## Shared environment
- `C:\gitRepositories` is one uv workspace: the root `pyproject.toml` lists every
  `NQCP-Phot-Git-*` repo as a member (except Simulations) and there is a single root `.venv`.
  Run `uv sync` from the root, not inside a repo.
- Optional extras: `attocube`, `upload` (needs the private Azure feed).
  A base `uv sync` works without either.
- `sync_uv_files.ps1 --pull | --push` copies `pyproject.toml`, `uv.lock` and `ty.toml` between
  the root and `NQCP-Phot-Git-GrafanaLogging\grafanaLogger\uv`. It overwrites files, so don't run it
  unless I ask.

## Conventions
- uv, `Python 3.13`, tests with `pytest`
