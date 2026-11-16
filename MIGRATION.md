# Migration checklist

## Before leaving the source Render account

1. Keep access to the source GitHub repositories and the source Render workspace.
2. Record every service's environment-variable **key names** and set the values aside in a secure password manager. Do not put secret values in Git.
3. Check whether the source PostgreSQL database is recoverable. At snapshot time it was suspended by billing and its listed expiry timestamp (2026-11-12) had passed. The inventory does not contain a database dump.
4. If the source database becomes accessible, create a PostgreSQL custom-format dump and verify it before relying on it. Restore it into a destination database and update the destination services' database connection settings securely.

## In the destination Render account

1. Connect the GitHub account that can access the source code repositories.
2. Review `render-blueprint.template.yaml`. Syncing it creates new services; it does not transfer or adopt the old service instances.
3. Confirm the destination regions and available plans. Free-plan availability and behavior may differ.
4. Create/restore the database separately only after confirming the data migration plan.
5. Add environment variables and secrets through the Render Dashboard or a secure secret manager.
6. Deploy each service and verify its health-check URL and application behavior.

## What this repository does not contain

- Environment-variable values, API keys, passwords, or database connection strings.
- PostgreSQL table contents or a database dump.
- Render service logs, deploy history, persistent disk contents, or account billing details.

This repository is an infrastructure reference, not a complete account export.
