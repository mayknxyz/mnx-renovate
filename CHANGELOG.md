# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Evaluate the preset's `schedule` in `Asia/Manila` instead of UTC: the weekly
  window is now 00:00–06:00 Monday Manila time (16:00–22:00 UTC Sunday),
  not 08:00–14:00 Manila as before (MNXI-809)

## [0.1.0] - 2026-10-23

### Added

- Adopt the repo into the `mks` kit: `.claude/settings.json` enables the
  `ult-kits` marketplace, and `CLAUDE.md` and `README.md` carry the managed
  `mks:init` blocks (MNXI-805)
