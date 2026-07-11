# Changelog

All notable changes to CRT (CRISPR Recognition Tool) are documented in this file.

## [1.3] - 2026-07-10

- Migrated project from the original room220.com hosting to GitHub.
- Renamed CRT main class to `CRTCLI`.
- Renamed GUI main class to `CRTGUI`.
- Standardized jar names to `CRT-GUI.jar` and `CRT-CLI.jar` (dropped version numbers from filenames).
- Updated `printUsage()` and all CLI error messages to reference `CRTCLI` instead of the old `crt` command name.
- Added `.gitignore`, `LICENSE`, and this changelog.
- Rebuilt `dist/CRT-CLI.jar` and `dist/CRT-GUI.jar` from current source.

## [1.2] — 2008-06-12

- CLI updated to use a more Unix-like command-line interface.
- CLI can now read input files from any directory, rather than requiring files to be in the working directory.

## [1.1] — 2007-03-14

- Initial public release.
- Graphical User Interface (GUI) version.
- Detects CRISPR repeats in FASTA-formatted DNA sequence files.
