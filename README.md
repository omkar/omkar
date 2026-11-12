# Omkar Nalamwar

Software architect focused on CI/CD, DevSecOps and platform engineering. Twelve years at NASA JPL leading software architecture and application teams for Mars and deep-space missions; now building and operating [CalculatedPath](https://calculatedpath.com) end to end.

My repositories are private, so here is how the main one is built and shipped.

## CalculatedPath: delivery pipeline

A college-planning platform for families (Next.js, TypeScript, PostgreSQL), run as a one-person platform team.

- **Pull-request gates.** Every change runs lint, typecheck, unit, database and Playwright end-to-end tests, plus dead-code checks, before it can merge. About 3,170 commits and 723 pull requests have gone through these gates.
- **Isolated environments.** Each change gets its own git worktree and its own Neon database branch, so tests never share data.
- **Release automation for data.** Datasets ship as immutable, versioned artifacts in Cloudflare R2 behind per-environment pointers. Releases promote staging to production, support dry runs, verify by reading back what production serves, and roll back automatically. Fault injection in staging exercises the rollback path.
- **Secure delivery.** Least-privilege token permissions on every workflow, environment-scoped secrets, read-only keys for test runs, production releases only from `main`, frozen lockfiles and weekly OSV vulnerability scans.
- **Operations.** A daily heartbeat checks pipeline and data freshness. Failed runs open one tracking issue that closes itself after a clean rerun, and a retention job prunes old releases.

13 GitHub Actions workflows · 65 schema migrations · 386 test files · 30+ specs and runbooks

## Background

- NASA Jet Propulsion Laboratory, Technical Group Supervisor (2013 – 2025): architecture review boards for multi-mission ground software and Deep Space Network upgrades
- M.S. Computer Science, Interactive Intelligence (now Artificial Intelligence), Georgia Tech · MBA, Information Technology, UC Irvine · B.S. Biochemistry, UC Riverside

[LinkedIn](https://www.linkedin.com/in/omkar-nalamwar/) · [calculatedpath.com](https://calculatedpath.com)
