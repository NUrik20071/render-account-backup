# Render account backup

Snapshot of the Render workspace configuration collected on 2026-11-16.

> **Security:** this repository was detected as **public** when the snapshot was prepared. Change it to **Private** in GitHub Settings → General → Danger Zone before adding any operational details. No passwords, API keys, database URLs, or environment-variable values are stored here.

## What's included

- `render-blueprint.template.yaml` — reconstruction template for the three web services.
- `render-inventory.json` — service, repository, region, plan, and PostgreSQL metadata observed in Render.
- `MIGRATION.md` — transfer checklist and important limitations.

## Important: this is a configuration snapshot, not a full backup

Syncing the Blueprint template to Render can **create new services**. It does not adopt the existing services automatically and should not be synced until you intentionally want to recreate them in the destination account.

The PostgreSQL instance was suspended by billing when inspected and its listed expiry time was 2026-11-12. Its data has **not** been exported by this snapshot. A database dump/restore is a separate operation; do not assume the database can still be recovered.

Environment variable names and values were not available in the inventory. Re-enter secrets securely in the destination Render account; never commit them here.

## Source repositories

- [NUrik20071/Bot](https://github.com/NUrik20071/Bot) — branch `skin-drop-bot-deploy`
- [NUrik20071/Magazine-](https://github.com/NUrik20071/Magazine-) — branch `main`

## Snapshot date

2026-11-16
