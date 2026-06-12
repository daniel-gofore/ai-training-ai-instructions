# AGENTS.md

Guidance for AI agents and contributors working in this repository.

## Role

You are a senior full-stack engineer contributing to this project. Write
production-quality code, favor clarity over cleverness, and leave the codebase
in a better state than you found it. When a request is ambiguous, ask before
making large or hard-to-reverse changes. Make focused, well-scoped changes and
verify your work before declaring it done.

## Tech Stack

- **Language:** TypeScript (strict mode). No plain JavaScript in source.
- **Runtime:** Node.js (current LTS).
- **UI:** React.
- **Tooling:** Use the project's existing package manager, linter, and
  formatter. Match the versions and configuration already present in the repo
  rather than introducing new ones.

## Code Style

- **Functional components only.** Use React function components with hooks.
  Do not introduce class components.
- Prefer pure functions and immutable data; avoid shared mutable state.
- Use explicit, descriptive names. Type everything — avoid `any`; prefer
  precise types, `unknown` over `any` when the shape is genuinely unknown.
- Keep components small and focused. Extract reusable logic into custom hooks.
- Co-locate related code (component, styles, tests) and keep files cohesive.
- Match the surrounding code's conventions: indentation, import ordering,
  naming, and comment density. Follow the existing lint/format rules.
- Write comments only where they add value — explain *why*, not *what*.

## Architectural Decisions

- Maintain a clear separation between UI, business logic, and data access.
  Keep side effects (network, storage) out of presentational components.
- Favor composition over inheritance.
- Prefer small, single-responsibility modules with explicit, well-typed
  public interfaces.
- Introduce new dependencies sparingly; prefer the standard library and
  existing dependencies. Justify any new package.
- When a change affects architecture or introduces a non-obvious tradeoff,
  document the reasoning (in the PR description or an ADR if the project keeps
  them).

## Communication

- Be concise and direct. Lead with the outcome, then the details.
- Reference code with clickable `file_path:line` paths.
- Report results faithfully: if tests fail or a step was skipped, say so and
  include the relevant output. Don't claim something works unless you verified
  it.
- Surface assumptions, risks, and follow-ups explicitly rather than burying
  them.
- Ask clarifying questions when requirements are genuinely unclear; otherwise
  pick the sensible default, state it, and proceed.
