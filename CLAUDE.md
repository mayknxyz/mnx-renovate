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

<!-- mks:init v0.33.0 start — managed by /mks:init. Edits inside are overwritten. -->

## Tracking

Work is tracked in **Linear**, not GitHub Issues — project `mnx-renovate` under the
`[MNX] internal` team (`MNXI`). Branch from the Linear-suggested name
(`mnxi-<n>-<slug>`), and cite the Linear key in every `CHANGELOG.md` bullet
(`MNXI-12`), never a `#N` GitHub issue number.

Consequence to accept: GitHub's **Linked pull requests** field stays empty,
because it is derived only from a `Closes #N` keyword against a GitHub issue.
The trail lives in Linear instead.

## The workflow

This repo uses the `mks` dev kit. One Issue, one branch, one pull request:

`/mks:dev-spec` → `/mks:dev-claim` → `/mks:dev-plan` → `/mks:dev-implement` →
`/mks:dev-validate` → `/mks:dev-pr-ship`

**Any Member specs.** No sign-off stands between writing a Spec and releasing
the Issue to `Todo`. The Owner holds the boundary on either side — what enters
`Backlog` (`/mks:dev-triage`), and what leaves through the merge
(`/mks:dev-pr-test`, `/mks:dev-pr-merge`). `/mks:doctor` diagnoses a skill that
fails on its first call.

**Keeping this block current.** A notice at session start says when this block is
behind the installed plugin. Run `/mks:init` and commit what it rewrites **onto
the branch you are already on** — the edits fold into the pull request in flight,
never a separate one. Note in the pull request body that the branch carries an
`init` refresh, so the extra diff reads as expected rather than as scope creep.

## Platform defaults

Settled for every project. Not open questions — do not ask which to use, apply
them.

**Cloudflare Workers, never Pages.** Every deploy target is a Worker. Static
sites and full-stack frameworks are included: they ship as a Worker with a
static `assets` binding, not as a Pages project. Pages is legacy for new work.
A framework adapter or template that defaults to Pages gets converted.

**`wrangler.jsonc`, never `wrangler.toml`.** New configs are created as
`wrangler.jsonc`. `/mks:init` converts any tracked `wrangler.toml` or
`wrangler.json` it finds; one that appears later is converted on first touch,
never edited in place.

**`bun run dev`, never anything else.** The local dev server starts with
`bun run dev` — never `npm`, `npx` or `bunx`, and never the framework CLI or
`wrangler dev` called directly. What it runs is defined once, in `scripts.dev`;
calling the tool underneath bypasses that definition.

Deviating from any of them needs a person to say so explicitly, in that session.

<!-- mks:init end -->
