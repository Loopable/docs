# AGENTS.md

You are working in the Loopable documentation repository.

Read `CONTRIBUTING.md` before changing anything. It contains the shared rules for contributors and agents, including accuracy, content boundaries, style, navigation, validation, and when to stop and ask for direction.

## About this project

- This is the [Mintlify](https://mintlify.com)-powered documentation site for Loopable.
- Pages are MDX files with YAML frontmatter.
- Configuration and navigation live in `docs.json`.
- Deployments are automatic on push to the default branch, so preview locally before pushing.
- For Mintlify product knowledge (components, configuration, writing standards), use the Mintlify skill: `npx skills add https://mintlify.com/docs`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP.
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP.

## Accuracy

The docs describe real, released Loopable behavior. The protocol specification in `loopable/protospec` is authoritative for protocol behavior, and `loopable/server` is the reference implementation.

Document only what exists. Do not document behaviors you guessed at or features that are unreleased or unsupported. When a behavior is ambiguous, check the specification and the server implementation. If it is still unclear, stop and ask.

Keep the docs consistent with `protospec` and `server`. A change that describes protocol or server behavior may require a corresponding change in that repository.

## Markdown

When creating or editing pages, use the `i-have-adhd` and `unslop` skills.

Documentation should be easy for a human to read.

Keep existing useful wording where possible. Do not rewrite large amounts of a page just to make it sound different.

## Style

- Use active voice and second person ("you").
- Keep sentences concise — one idea per sentence.
- Use sentence case for headings.
- Bold for UI elements: Click **Settings**.
- Use code formatting for file names, commands, paths, and code references.
- Keep existing useful wording. Do not rewrite pages just to make them sound different.

## Keep changes small

Make the smallest change that completely solves the task. Do not make unrelated improvements, refactors, cleanups, or "while I'm here" changes. A focused addition to an existing page is better than a restructure.

## Navigation and content boundaries

Add new pages to the appropriate group in `docs.json`. Keep page titles, descriptions, navigation entries, and links consistent, and check for broken links.

Do not document internal implementation details or anything not relevant to users of Loopable. Do not put real credentials, private keys, or user data in examples.

Draft and unfinished pages go in `drafts/` or as `*.draft.mdx`; Mintlify ignores them. Remove draft markers before finishing.

## Tests and validation

Preview locally before relying on an automatic deploy:

- Run `mint dev` at the root of the documentation where `docs.json` is.
- Run `mint update` if the CLI is stale.
- Verify the page renders as intended and links resolve.

## Protected repository files

Do not modify `README.md`, `AGENTS.md`, `CONTRIBUTING.md`, `LICENSE`, or other repository-policy or deployment files during an ordinary task. Change them only when the user explicitly asks for that specific documentation or policy change.

## Before finishing

Inspect the final diff and verify that every changed file belongs to the requested task. Use Conventional Commits (`type(scope): description`) for commit messages, matching the rest of Loopable.