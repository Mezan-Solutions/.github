# Contributing at PlanetColors (Odoo)

## Repos
| Repo | What's in it | Branches |
|---|---|---|
| `client-<name>` | One per client: their custom modules + pinned submodules | `main` (prod), `staging`, `feature/*` |
| `planet-colors-addons` | Our reusable `pc_*` modules | one per Odoo version: `18.0`, `19.0`, `20.0` |

## Module naming
- All our modules start with **`pc_`** (our company prefix; Odoo's guidelines recommend a company prefix for non-core modules).
- After the prefix, name the app you extend: `pc_sale_discount`, `pc_stock_barcode_labels`, `pc_l10n_et_reports`.
- Client-only modules: `pc_<client>_<feature>`, e.g. `pc_<client>_invoice_layout`.

## Branches (client repos)
- `main` = production. **Never push directly.**
- `staging` = what the client tests. **Never push directly.**
- Work on `feature/<issue#>-<short-name>` from `staging`, e.g. `feature/42-sale-discount`.
- Hotfix: `hotfix/<issue#>-<short-name>` from `main`, merged to `main`, then back into `staging`.
- Free plan note: GitHub does not *enforce* these rules on our private repos. We follow them by agreement; only leads merge.

## Commit messages (Odoo style)
```
[TAG] module: short summary (ideally < 50 chars)

Why the change was needed (not just what).

Closes #42
```
Tags: `[FIX]` bug fix, `[IMP]` improvement, `[ADD]` new module, `[REM]` remove, `[REF]` refactor,
`[MOV]` move files, `[REV]` revert, `[REL]` release, `[I18N]` translations, `[PERF]` performance,
`[CLN]` cleanup, `[LINT]` lint, `[MERGE]` merge. We also use `[MIG]` for version migrations (OCA convention).

Examples:
```
[FIX] pc_sale_discount: round discount before tax
[ADD] pc_<client>_invoice_layout: new invoice report for <Client Name>
[MIG] pc_stock_report: migrate to 19.0
```

## Pull request flow
1. Open an issue (bug or change request) first.
2. Branch from `staging`, commit in small steps, run `pre-commit run --all-files`.
3. Open a PR into `staging` and fill the PR checklist (manifest version bump, migration, access rights, etc.).
4. CI must be green (we don't merge red builds, even though Free can't block it).
5. One lead reviews and merges. Test on the staging build (neutralized prod copy).
6. Release: a lead opens `staging` -> `main`, merges after client sign-off, and tags the release.

## Module version numbers
`<odoo version>.<major>.<minor>.<patch>`, e.g. `19.0.1.2.0`. Bump the version in every PR that changes
data, fields or views so Odoo upgrades the module on deploy. Add a migration script when existing data must change.

## Never commit
Passwords, API keys, `odoo.conf` with real credentials, database dumps, `filestore/`, client personal data.
