# GitHub Profile Design

## Purpose

Present Tibetan777 as a software-engineering builder through concrete engineering evidence rather than decorative widgets or unsupported skill claims.

## Design principles

- Evidence before claims.
- Static content carries the profile; no critical dependency on third-party image APIs.
- Minimal visual noise and no badge wall, visitor counter, trophies, snake animation, or subjective skill percentages.
- Dark/neutral visual identity supplied primarily by the provided high-contrast portrait and terminal-inspired section labels.
- Mobile-safe Markdown/HTML with no wide layout tables.
- Public profile does not expose private repository URLs.

## Sections

1. Hero portrait and concise positioning.
2. `~/ whoami` summary.
3. `~/ currently-building` featured Portfolio Simulation project.
4. `~/ engineering-stack` verified technology groups.
5. `~/ selected-work` capability-based summaries that avoid disclosing private repository names.
6. `~/ engineering-principles` compact engineering philosophy.
7. `~/ activity` note explaining current private-development posture.

## Evidence basis

The implementation was derived from accessible repository evidence, including:

- Portfolio Simulation: TypeScript monorepo, React/Vite, Node.js, Cloudflare Workers, MongoDB, Redis-compatible cache, stochastic simulation engines, walk-forward analysis, security verification, and an external test deployment.
- A React Native project: React Native 0.82.x, TypeScript, navigation, AsyncStorage, Express, and PostgreSQL.
- A full-stack web project: React/Vite, Express, MySQL, Redis, JWT, Helmet, rate limiting, and related backend tooling.

Private project names and private repository links are intentionally not exposed in the public README except for the public-facing Portfolio Simulation product name and its external test deployment.

## Automation

None in the initial version.

Reason: the profile remains more reliable, cheaper, easier to audit, and lower-maintenance without third-party profile-stat actions. GitHub already provides native contribution activity outside the README.

## External dependencies

The README has no runtime third-party widget dependency. The only repository asset is the provided portrait image. The Portfolio Simulation external test deployment is linked as a project destination.

## Security decisions

- No GitHub Actions in v1.
- No PATs or long-lived secrets.
- No third-party profile statistics endpoints.
- No public links to private repositories.
- No unsupported claims or synthetic skill metrics.

## Updating the profile

Edit `README.md` for copy/sections and replace `assets/profile/profile.webp` when changing the portrait. Keep links verifiable and remove stale project claims as project status changes.

## Rollback procedure

If this profile repository is version-controlled normally, revert the profile commit rather than rewriting history:

```bash
git log --oneline
git revert <profile-commit-sha>
git push origin main
```

If changes are staged on a feature branch before merge, simply delete or abandon the feature branch.
