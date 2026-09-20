# CONTRIBUTING.md

This repository contains the Loopable documentation site, built on Mintlify. It is the user-facing documentation for the Loopable Protocol and the Loopable Instance Server.

For Mintlify product knowledge — components, configuration, and writing standards — install the Mintlify skill: `npx skills add https://mintlify.com/docs`

## Before changing content

Read the relevant existing pages, the `docs.json` navigation, and the descriptions of the behavior you are documenting before making changes. Follow the repository's existing patterns. Do not add a second mechanism when one already exists.

The protocol specification at [github.com/loopable/protospec](https://github.com/loopable/protospec) is authoritative for protocol behavior, and `loopable/server` is the reference implementation. Keep the docs consistent with both.

## Accuracy

The docs must describe real, released behavior. They are not a design document.

Every documented behavior must correspond one-to-one with the product and the protocol specification. Do not guess at behavior, reinterpret the specification for convenience, or document a server-only or local interpretation.

When the specification or implementation is ambiguous, incomplete, or appears incorrect, stop and raise the issue rather than documenting a guess.

Changes that describe protocol behavior may require a corresponding change or discussion in `protospec`. Changes that describe server behavior may require a corresponding change in `server`.

## Content boundaries

Document what users of Loopable need: guides, reference, and behavior that affects how they use instances and federation.

Do not document internal implementation details, unreleased features, or anything that would mislead a user. Draft and unfinished content belongs in `drafts/` or as `*.draft.mdx` files.

## Privacy and security

Protect user content, credentials, private keys, identifiers, and instance data. Do not place real secrets or user data in the repository, examples, or pull requests. Use clearly fake values in examples.

## Style

- Use active voice and second person ("you").
- Keep sentences concise — one idea per sentence.
- Use sentence case for headings.
- Bold for UI elements: Click **Settings**.
- Use code formatting for file names, commands, paths, and code references.

Keep existing useful wording where possible. Do not rewrite large amounts of a page just to make it sound different.

## Navigation and configuration

Add new pages to the appropriate group in `docs.json`. Keep page titles, descriptions, navigation entries, and links consistent, and check for broken links. A page that exists but cannot be navigated to is not documentation.

## Licensing

Follow the repository's license for contributed content. Do not copy material, examples, assets, or diagrams of unclear origin or incompatible licensing. Preserve license and attribution notices.

## Tests and validation

Preview locally before relying on automatic deployment:

```bash
mint dev
```

Run from the root of the documentation where `docs.json` is located. Run `mint update` to ensure the CLI is current. Verify the changed pages render as intended and that links resolve.

## Protected repository files

Do not modify `README.md`, `AGENTS.md`, `CONTRIBUTING.md`, `LICENSE`, or other repository-policy, security, or deployment files during an ordinary implementation task. Such changes require explicit user authorization for the specific file and purpose.

## Pull requests and commits

Keep each pull request focused on one coherent change. Explain what changed, why it is needed, how it was validated, and any effects on navigation, accuracy, or deployed content.

When using AI tools or agents, the contributor remains responsible for understanding and reviewing the result. Remove unrelated generated changes before submitting the pull request.

Use Conventional Commits when writing commit messages, matching the rest of Loopable:

```
type(scope): description
```

Examples:

- `docs: add federation guide`
- `fix(docs.json): correct quickstart link`

Use `!` or a `BREAKING CHANGE` footer when a commit introduces a breaking change. For documentation, that means things like renamed or removed pages that invalidate existing links, which must be called out so navigation and migration can be handled.