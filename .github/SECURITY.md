# Security policy

## Reporting a vulnerability
Please do **not** open a public issue. Email **security@TODO-company-domain** <!-- TODO: real address -->
with steps to reproduce. We reply within 3 working days.

## Internal rules
- 2FA is required for everyone in the organization.
- Secrets live in GitHub repository secrets, Odoo.sh settings, or the server's environment, never in git.
- If a secret was committed: rotate it immediately (removing the commit is not enough), then tell a lead.
- Production database copies used for staging/dev are always **neutralized** (`odoo-bin neutralize`).
- Client data is never copied to personal laptops without a lead's approval.
