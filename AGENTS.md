# AGENTS.md

`syncs.toml` is the single Komodo resource file for the estate: the `[[resource_sync]]` entries Core pulls, the shared `[[repo]]` that stacks link to as `linked_repo`, and Core-level `[[procedure]]`s (backup, prune, global auto update).
It is applied by a meta sync created once by `brumi1024/homelab-infra` (`06_deploy_komodo_op.yml`), so a repository URL or branch changes here and nowhere else.

- Stack definitions live in the target repos (`brumi1024/komodo-app-stacks`, `brumi1024/deploy-komodo-op`); this repo only says where to pull them from and how.
- Secrets never appear here; they come from 1Password through komodo-op.
- Use `$komodo-stack-lifecycle` when a stack lifecycle change also affects sync ownership or repository topology.
