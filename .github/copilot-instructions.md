# Portmaster Assist contributor instructions

## Current project status

This repository is a small collection of legacy FreeBSD maintenance scripts, not
an actively maintained application with a full build or test pipeline.

Current status of the main scripts:

- `refresh`: legacy but intended for use in a live FreeBSD ports environment.
- `update`: legacy but intended for use in a live FreeBSD ports environment.
- `pmmove`: explicitly marked as broken and should not be used as part of the
  normal workflow until it is repaired.

Do not treat this repository as a general-purpose cross-platform shell project.
The scripts are designed for FreeBSD, `pkg`, `portmaster`, and the `/usr/ports`
ports tree.

## Commands

This repository has no build system, automated test suite, or linter. There is
therefore no full-suite or single-test command.

Use light validation when changing shell scripts:

```sh
sh -n ./refresh
sh -n ./update
```

Do not rely on `pmmove` as a normal validation target. The script currently exits
immediately with a warning that it is broken, so syntax validation alone is not a
signal of safe runtime behavior.

The scripts operate on the live FreeBSD ports tree and installed packages. Do
not use `refresh`, `update`, or `pmmove` as routine local validation; run them
only in an intended FreeBSD / Portmaster environment. `./refresh help` is the
non-mutating way to inspect `refresh` arguments.

## Architecture and workflow

Portmaster Assist consists of three executable scripts kept in one working
directory:

1. `refresh` updates `/usr/ports` from its Git `main` branch, starts
   `portmaster -L` in the background, writes available package upgrades to
   `refresh.log`, and appends applicable `pkg updating` entries to
   `refresh-updating.log`. Its `refresh.meta` timestamp scopes those updating
   entries to changes since the last default or reset refresh.
2. `update` reads the generated `portmaster.log` before running `portmaster -a`.
   It blocks when that log is still in use and supports a failed-run resume flow
   via `./update failed` or the interactive `~/portmasterfail.txt` path.
3. `pmmove` is a known-broken legacy path. It exits immediately with a warning
   and should not be used in normal operations until it is rewritten or fixed.

The scripts require FreeBSD tooling: `pkg`, `portmaster`, and, for `refresh`,
Git. Keep their prerequisite checks and nonzero failure behavior intact.

## Repository-specific conventions

- `refresh` and `update` use POSIX `/bin/sh`; `pmmove` is legacy and currently
  disabled rather than a supported workflow. Preserve the target shell syntax and
  idioms rather than applying Bash syntax across the scripts.
- Compute paths relative to the script location (`WP=$(dirname $0)`) for
  generated state and logs. The tools are expected to work when called outside
  the repository directory.
- Generated `*.log`, `*.meta`, and `*.conf` files are intentionally ignored.
  `update.conf` is created on first execution and uses `ignore=<port>` entries
  that expand into Portmaster `-x` exclusions; do not add local generated files
  to version control.
- Keep the `INIT section`, `FUNCTIONS section`, and `MAIN section` layout in the
  scripts. Configuration and prerequisites belong in initialization; operational
  actions remain in named functions.
- The log files are handoff state between scripts, not merely diagnostics:
  `portmaster.log` gates concurrent refresh/update work and records moved ports,
  while `refresh.log` and `refresh-updating.log` report update availability and
  required manual actions.
- When changing this project, prefer conservative updates that preserve the legacy
  FreeBSD workflow and do not assume a broader modernization effort is already in
  progress unless the repository explicitly documents it.
