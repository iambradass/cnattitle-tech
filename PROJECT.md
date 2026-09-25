# CNAT legacy review-site source

Shared starting point for Codex and Claude Code. This file holds current workflow facts; preserve the detailed references below.

## Source and release
- Source: this repository root, including a dedicated worktree of it.
- Repository: `https://github.com/iambradass/cnattitle-tech.git`.
- Release: Historical Hostinger Git source. Reverify current domain ownership/routing before deployment; the September 21 account notes record the apex moving to GHL.
- Preserve historical review and thank-you routes. Local source is not proof that cnattitle.tech currently serves this checkout. Never change DNS or redirects as part of routine local setup.

## Verify the requested change
- Run `python3 .agent-workflow/verify.py`; use `--base <reviewed-base>` when the change includes commits, or `--checks-only` to run native checks.
- The exact reviewed commands are in `.agent-workflow/checks.json`; `--list` shows coverage. Missing prerequisites and existing failures must be reported, not silently skipped.
- For changed web behavior, check the actual flow at 375px and desktop. For generated reports/documents, inspect the rendered output. Syntax or unit checks alone do not prove visual or live integration behavior.
- Generate required build assets/cache versions before final release checks. After an authorized release, verify the deployed revision and relevant live behavior. Preserve unrelated staged/unstaged work; do not stage everything.

## Continue across sessions
Read `.agent-workflow/STATUS.md` when resuming. Update it after meaningful work with outcomes, validation, remaining steps, and actual deployment state. It points to earlier handoffs; it does not replace them. Current user instructions and verified current state govern over dated notes.

## Detailed context, only as needed
- `README.md`
- `.htaccess`
