## What & why
<!-- One or two sentences. Link the issue: "Closes #123" -->

Closes #

**Odoo version:** <!-- 18.0 / 19.0 / 20.0 -->
**Modules touched:** <!-- e.g. pc_sale_discount, pc_stock_report -->
**Target branch:** <!-- feature/* -> staging, or staging -> main (release) -->

## Type
- [ ] [FIX] bug fix
- [ ] [IMP] improvement
- [ ] [ADD] new module
- [ ] [REF] refactor
- [ ] [MIG] migration to a new Odoo version
- [ ] Other:

## Odoo checklist
- [ ] `__manifest__.py` **version bumped** (e.g. `19.0.1.0.1`) so the module upgrades on deploy
- [ ] **Migration script** added in `migrations/<new_version>/` (`pre-`/`post-migrate.py`) if fields, models or data changed (or N/A)
- [ ] **`security/ir.model.access.csv`** has a line for every new model (or N/A)
- [ ] **Record rules** checked (multi-company / per-user access) (or N/A)
- [ ] **Translations:** `i18n/<module>.pot` regenerated if user-facing strings changed (or N/A)
- [ ] **Tested on staging** with a **neutralized copy** of production data (no real emails, payments or crons)
- [ ] **Demo data** still loads (Odoo.sh dev builds and CI install with demo data)
- [ ] New Python dependencies added to `requirements.txt` (or N/A)
- [ ] **No hardcoded credentials**, API keys, IPs or client passwords; secrets use system parameters / env vars
- [ ] No `print()`, `pdb`, or commented-out code left behind
- [ ] Views use `inherit_id` + XPath; no core Odoo files edited
- [ ] pre-commit passes locally (`pre-commit run --all-files`)

## How to test
1.
2.

## Screenshots (UI changes)

## Deploy notes
<!-- Module upgrades needed, settings to change, data to fix, downtime -->
