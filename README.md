# mnx-renovate

Shared [Renovate](https://docs.renovatebot.com/) preset for every repo across
`mayknxyz`, `MNX-Ventures`, `Madali-LLC` and `optimified`.

Public on purpose: Renovate installs in the other accounts can only read a
preset they can see. It holds update rules only — no secrets.

## Use it

In a repo's `renovate.json`:

```json
{ "extends": ["github>mayknxyz/mnx-renovate"] }
```

## What it does

- Runs Mondays before 6am; security fixes any time.
- Waits 7 days after a release before proposing it.
- One grouped `non-major` PR for minor + patch updates.
- One PR per major update, labeled `major`.
- No automerge, no Dependency Dashboard (work is tracked in Linear).

## Per-repo overrides

Add rules after `extends` in that repo's `renovate.json`:

```json
{
  "extends": ["github>mayknxyz/mnx-renovate"],
  "packageRules": [
    { "description": "Stay on Astro 5 until X", "matchPackageNames": ["astro"], "allowedVersions": "5.x" },
    { "description": "Frozen because Y", "matchPackageNames": ["svelte"], "enabled": false }
  ]
}
```

<!-- mks:init v0.33.0 start — managed by /mks:init. Edits inside are overwritten. -->

## Development

This repo uses [`mks`](https://github.com/MNX-Ventures/ult-kits), the team kit.
Install it once per machine:

```
/plugin marketplace add MNX-Ventures/ult-kits
/plugin install mks@ult-kits
```

Then `/mks:doctor` to check the setup. Work is tracked in Linear under the
`mnx-renovate` project — GitHub Issues are off. Full setup, including git
credentials: [ult-kits INSTALL.md](https://github.com/MNX-Ventures/ult-kits/blob/main/INSTALL.md).

<!-- mks:init end -->
