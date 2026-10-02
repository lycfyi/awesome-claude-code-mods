# Contribution Guidelines

Thanks for helping. This list stays short on purpose, so every entry needs to clear the bar below. Please note that this project is released with a [Contributor Code of Conduct](code-of-conduct.md). By participating in this project you agree to abide by its terms.

## What counts as a mod

A Claude Code plugin whose `hooks/hooks.json` lists a hooks module (`"modules": ["./register.ts"]` or similar) that runs inside Claude Code through the [mods API](https://code.claude.com/docs/en/plugins/mods/overview). Settings hooks that run shell commands, skills, MCP servers, status line scripts and output styles are not mods; [Awesome Claude Code](https://github.com/hesreallyhim/awesome-claude-code) covers those.

## Admission bar

- The repository is public, not archived, and has an open source license.
- The README says what the mod does and how to install it (`/plugin marketplace add …` and `/plugin install …`).
- `claude plugin validate <mod-dir>` passes on the current Claude Code release. Plugin names that start with `claude-` now fail validation, so rename those first.
- You ran it yourself and name the Claude Code version you tested it on.
- If it draws anything, the PR includes a screenshot or GIF.
- It is the original work, not a copy or repackage of another mod.
- It does something that no entry in the list already does better.

Submitting your own mod is fine as long as it meets the bar.

## Adding an entry

1. Edit [readme.md](readme.md) on GitHub ([how to edit a file](https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files)); it forks the repository for you.
2. Add one line at the bottom of the section that fits:

   ```md
   - [plugin-name](https://github.com/owner/repo) - What it draws or blocks, in one sentence.
   ```

   - Use the plugin's `name` from `.claude-plugin/plugin.json` as the link text.
   - Link the mod's own directory when the repository holds several mods (`…/tree/main/<mod-dir>`).
   - Start the description with a capital letter and end it with a period. Describe what it does, not how great it is; no emoji, no "you".
3. Open a pull request titled `Add plugin-name` and fill in the template. One mod per pull request.

The `awesome-lint` and link checks must pass before a pull request is merged.

## Updating or removing an entry

Open a pull request explaining why. Entries are removed when the repository is archived or deleted, when the mod stops validating on the current Claude Code release, or when it goes six months without a commit.
