# Agent Rules

## Commits

- Follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).
- Always use a scope: `type(scope): subject`
- Keep subjects short, imperative, and without a trailing period.
- Prefer narrow scopes such as `core`, `docs`, `landing`, `filters`, `twoslash`, `release`, `ci`, or `monorepo`.

## Docs

- Use Twoslash for code examples when setting up or updating docs examples.
- Make sure Twoslash examples actually compile and do not introduce dev server errors.
- Run docs validation commands sequentially, not in parallel. In particular, avoid running `check:content`, `generate:twoslash`, `nuxt prepare`, `nuxt build`, or other Nuxt content/Twoslash validation steps concurrently because the docs toolchain can hit SQLite/content cache locking and flaky failures.
- When docs UI or layout changes matter, use the browser agent to verify the rendered result.

## Examples

- `packages/core/examples/kitchen-sink-*` must reflect the current user-facing feature surface.
- Any new user-facing feature must be reflected in the kitchen-sink example unless there is a clear, documented reason not to.
- If a feature is intentionally omitted from kitchen sink, explain why in the PR or working notes.
- Prefer one focused kitchen-sink usage per feature rather than many redundant variations.

<!--VITE PLUS START-->

# Using Vite+, the Unified Toolchain for the Web

This project is using Vite+, a unified toolchain built on top of Vite, Rolldown, Vitest, tsdown, Oxlint, Oxfmt, and Vite Task. Vite+ wraps runtime management, package management, and frontend tooling in a single global CLI called `vp`. Vite+ is distinct from Vite, and it invokes Vite through `vp dev` and `vp build`. Run `vp help` to print a list of commands and `vp <command> --help` for information about a specific command.

Docs are local at `node_modules/vite-plus/docs` or online at https://viteplus.dev/guide/.

## Review Checklist

- [ ] Run `vp install` after pulling remote changes and before getting started.
- [ ] Run `vp check` and `vp test` to format, lint, type check and test changes.
- [ ] Check if there are `vite.config.ts` tasks or `package.json` scripts necessary for validation, run via `vp run <script>`.
- [ ] If setup, runtime, or package-manager behavior looks wrong, run `vp env doctor` and include its output when asking for help.

<!--VITE PLUS END-->
