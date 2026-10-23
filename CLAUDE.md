# mnx-renovate

Shared Renovate preset (`default.json`) extended by repos across `mayknxyz`,
`MNX-Ventures`, `Madali-LLC` and `optimified` via
`github>mayknxyz/mnx-renovate`.

- The repo is public on purpose: Renovate installs in other accounts can only
  read a preset they can see. Never commit secrets.
- A change to `default.json` affects every consuming repo on its next Renovate
  run. Keep changes small and note them in `CHANGELOG.md`.
- Work is tracked in Linear (`[MNX] internal`, project `mnx-renovate`), not
  GitHub Issues.
