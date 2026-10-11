# Awesome Claude Code Mods [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Mods are small TypeScript or JavaScript functions that change how Claude Code works: they hook into tool calls, prompts and screen rendering, and can draw panes, status lines and toasts inside the session.

Mods need Claude Code 2.1.287 or later. They ship as plugins, so most install with `/plugin marketplace add owner/repo` followed by `/plugin install name@marketplace`; each entry's README has the exact commands. Mods are not sandboxed and run with your permissions, so read the source before you install one.

This is a short list on purpose. Every entry passed `claude plugin validate` on the Claude Code release current when it was added, and every community entry has an open source license and had a commit in the 30 days before it was listed. For an index of every mod on GitHub, see the Related section.

## Contents

- [Official](#official)
- [Session and Context](#session-and-context)
- [Git and Code Review](#git-and-code-review)
- [Safety and Guards](#safety-and-guards)
- [Agents and Workflows](#agents-and-workflows)
- [Just for Fun](#just-for-fun)
- [Building Mods](#building-mods)
- [Related](#related)

## Official

Built into Claude Code, published as samples by Anthropic, or listed in Anthropic's official marketplace.

- [diff](https://github.com/anthropics/claude-code/tree/main/mods/diff) - The built-in `/diff` pane, showing the session's uncommitted changes file by file and refreshing as Claude edits.
- [agents-md](https://github.com/anthropics/claude-code/tree/main/mods/agents-md) - Built-in mod that reads `AGENTS.md` the way Claude Code reads `CLAUDE.md`, switched by the `instructionFiles` setting.
- [sec-default](https://github.com/anthropics/claude-code/tree/main/mods/sec-default) - Built-in organization guard that loads first on Team and Enterprise plans and keeps the organization's hooks, settings and tool policy out of reach of user-installed mods.
- [token-weather](https://github.com/anthropics/claude-code-playground/tree/main/claude-code/mods/token-weather) - Sample that draws a weather forecast of the context window above the prompt, with the fill percentage and a chart of recent turns.
- [blast-radius](https://github.com/anthropics/claude-code-playground/tree/main/claude-code/mods/blast-radius) - Sample that holds risky shell commands such as `rm -rf`, `git reset --hard` and force pushes, shows what they would change in a pane, and waits for Proceed or Cancel.
- [replay-theater](https://github.com/anthropics/claude-code-playground/tree/main/claude-code/mods/replay-theater) - Sample that steps through the file edits Claude made in the last turn, one diff at a time.
- [code-modernization](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/code-modernization) - Guided modernization of a legacy codebase behind `/modernize`, with the assessment, code map and plan drawn in panes.

## Session and Context

- [cctop](https://github.com/tomstagl/cctop) - A btop-style dashboard pane with context fill, tokens, cost, cache hit ratio, rate limits and per-tool latency.
- [burn-meter](https://github.com/OneWave-AI/claude-code-mods/tree/main/burn-meter) - Session spend as a burning fuse above the prompt, with 5-hour and weekly plan-limit bars and a pane of per-turn cost.
- [cache-tax](https://github.com/karanb192/cache-tax) - Keeps the one-hour prompt cache warm while you step away, and stops a cold send once to show what it will cost.
- [contextsaver](https://github.com/AlmogBaku/ContextSaver) - Spots wasteful workflows and habits in a session, names the cheaper alternative with its measured cost, and applies the fix in one click.
- [lcm](https://github.com/lossless-claude/lcm) - Lossless context management that summarizes into a DAG while keeping every message retrievable.
- [prompt-rail](https://github.com/oikon48/prompt-rail) - A rail of the session's prompts beside the transcript, where hovering reads a prompt and clicking jumps to it.
- [aside](https://github.com/JayDoubleu/aside) - A read-only side chat in a pane, answered by a tool-less fork of the session that writes nothing back to the main thread.
- [next-steps](https://github.com/anthropics/claude-plugins-community/tree/main/next-steps) - Suggests up to three next prompts above the input after each turn, and a number key drafts one into the prompt box.

## Git and Code Review

- [cc-pr-tracker](https://github.com/sezaakgun/cc-pr-tracker) - One line per watched pull request above the prompt with merge state, review and required checks, plus a toast when any of them changes.
- [pull-request-pane](https://github.com/meganemura/pull-request-pane) - The pull requests and issues related to the session in a pane, where you mark spans of text and send all the comments as one prompt.
- [diff-review](https://github.com/stefanoshea/diff-review) - A branch diff in a pane where you and Claude draft line comments, sent to GitHub as a pending review.

## Safety and Guards

- [secret-redactor](https://github.com/ray-amjad/awesome-claude-code-function-hooks/tree/main/plugins/secret-redactor) - Swaps secrets, email addresses and IP addresses for stable placeholders before the model sees them, and restores the real values inside tool calls.
- [honmoon-redact](https://github.com/pleaseai/honmoon/tree/main/packages/claude-plugin) - Redacts API keys and sensitive identifiers from Read, Bash, Grep and WebFetch output, and blocks prompts that carry secrets.
- [launch-codes](https://github.com/OneWave-AI/claude-code-mods/tree/main/launch-codes) - Makes dangerous Bash commands open a red-alert pane and wait for a code before they run.
- [scope-guard](https://github.com/yash-gadodia/claude-mods/tree/main/scope-guard) - Counts the files a turn edits and stops at a threshold, so the goal gets restated before a small ask becomes a refactor.
- [merge-gate](https://github.com/yash-gadodia/claude-mods/tree/main/merge-gate) - Denies `gh pr merge`, merges into main and pushes to main unless your latest message contains the word merge.

## Agents and Workflows

- [agent-flow](https://github.com/Charlie0113-T/claude-agent-flow) - A live tree of the session's subagents and teammates in a pane beside the transcript.
- [flowpane](https://github.com/mpolatcan/flowpane) - Replaces the workflow progress list with a live phase graph or timeline showing each agent's state, timing and token spend.
- [terminal-browser](https://github.com/zenbu-labs/terminal-browser) - A web browser inside Claude Code that previews sites and HTML files and that the agent can drive.

## Just for Fun

- [mindful-claude](https://github.com/halluton/Mindful-Claude) - Guided breathing exercises above the prompt while Claude works, with the spinner counting the breath.
- [cc-arcade](https://github.com/sezaakgun/cc-arcade) - Nine games above the prompt that pause when Claude finishes, plus a pet fed by Claude's tests, commits and edits.
- [pixelband](https://github.com/furqan-khan07/pixelband) - Animated pixel art or your own image above the prompt, reacting as turns start, finish and fail.
- [boss-fight](https://github.com/OneWave-AI/claude-code-mods/tree/main/boss-fight) - Failing tests spawn a pixel boss with one hit point per failure, and every run that fixes tests lands a hit.
- [swear-slap](https://github.com/paragpandyareal/swear-slap) - Swear in a prompt and a pixel-art hand slaps the band above it instead of sending the message, then puts a polite version back in your prompt box, with a swear jar and a slap sound, drawn locally with no model calls or network.

## Building Mods

- [Mods overview](https://code.claude.com/docs/en/plugins/mods/overview) - What mods are, what they can change and which version they need.
- [Create a mod](https://code.claude.com/docs/en/plugins/mods/create) - Writing, loading and hot-reloading a first mod.
- [Draw in the interface](https://code.claude.com/docs/en/plugins/mods/interface) - Panes, the band above the prompt, status lines, toasts and redrawing built-in parts of the screen.
- [Interface gallery](https://code.claude.com/docs/en/plugins/mods/gallery) - Every element a mod can draw, with sample code and terminal screenshots.
- [Mods API](https://code.claude.com/docs/en/plugins/mods/api) - The `$` object every hook receives.
- [Test a mod](https://code.claude.com/docs/en/plugins/mods/test) - Testing mods with `claude plugin test`.
- [Mods reference](https://code.claude.com/docs/en/plugins/mods/reference) - Events, elements and file layout.
- [Type declarations](https://github.com/anthropics/claude-code/blob/main/mods/types/claude-code.d.ts) - Full types for the `claude-code` module.
- [Launch announcement](https://claude.com/blog/claude-code-mods) - Anthropic's post introducing mods.
- [Mods discussion](https://github.com/anthropics/claude-code/issues/91870) - Open GitHub issue on extending Claude Code through mods, with more than 200 comments.
- [Claude Code playground](https://github.com/anthropics/claude-code-playground) - Anthropic's repository of sample mods with walkthrough READMEs.

## Related

- [karanb192/awesome-claude-code-mods](https://github.com/karanb192/awesome-claude-code-mods) - Every Claude Code mod on GitHub, with a nightly scan of the events and APIs each one can reach.
- [Awesome Claude Code](https://github.com/hesreallyhim/awesome-claude-code) - Skills, hooks, slash commands and other resources for Claude Code.

## Contributing

Contributions welcome. Read the [contribution guidelines](contributing.md) first.
