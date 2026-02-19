# CLAUDE.md

Project-level guidance for building the RealWorld "Conduit" app.

## Spec

The full RealWorld specification lives in `../../realworld-docs/`. Read the backend endpoints, frontend routing, and feature requirements from there.

## Conventions

- Follow the rules in `rules/` for coding style, testing, and security
- Use small, focused commits with conventional commit messages
- Write tests alongside or before production code (TDD preferred)
- Keep modules aligned with RealWorld domain boundaries (users, articles, comments, tags, profiles)

## Token Tracking

After each session, log token usage to `tracking/session-log.jsonl` using the schema in `../common/tracking-template.json`.
