# Talk To Me — 4D Dialogue Guardrails

A portable, platform-agnostic AI skill that operationalizes Anthropic
Academy's **4D prompting framework** as a standing set of guardrails against
the most common AI failure modes:

- **Hallucination** — stating guesses as verified fact
- **Silent failure** — quietly skipping part of a task/instruction instead of flagging it
- **Broken reasoning** — multi-step answers with a weak or unsupported link nobody checked
- **Unwarranted confidence** — sounding equally sure about solid facts and shaky guesses
- **Sycophancy** — agreeing with the user instead of checking them
- **Knowledge cutoff blind spots** — answering time-sensitive questions as if training data were current

...plus one "guest star" behavior straight out of the 4D framework: asking
the AI to **optimize your prompt before answering it** (while preserving
your original intent, or asking for clarification if that intent is
unclear), and declaring that rewrite up front.

The full ruleset lives in [`SKILL.md`](./SKILL.md).

## Manual invocation only — by design

**This skill has no automatic trigger.** It will not silently activate
itself based on keywords or context. You (the user) invoke it explicitly
when you want it active for a conversation.

If you want it active by default in *every* conversation on your platform,
that is a setting you turn on yourself, on your own AI system — this skill
intentionally does not assume that for you. See the platform notes below.

## How to import / use it

### Claude (claude.ai / Claude Code)

- **Claude.ai (Skills):** import this repository (or just the contents of
  `SKILL.md`) as a custom skill in your Skills settings. Once added, invoke
  it by name in a conversation when you want its rules applied.
- **Claude Code (project or user skill):** drop this folder into
  `.claude/skills/<name>/` (project-level) or
  `~/.claude/skills/<name>/` (user-level), keeping the `SKILL.md` filename.
  Invoke it manually as a skill in your session (e.g. `/the-talk-me-as-per-anthropic-academy-skill`).
- **Always-on for yourself:** if you want these rules applied automatically
  in every session without invoking the skill each time, add the contents
  of `SKILL.md` to your Claude custom instructions / project instructions
  in your account or project settings. That is a setting on *your* account,
  not something this skill does on its own.

### Other AI assistants / chatbots

Most assistants that support a "custom instructions," "system prompt," or
"persona" field can use this the same way:

1. Copy the body of `SKILL.md` (everything after the frontmatter).
2. Paste it into that assistant's custom-instructions / system-prompt field,
   or into the start of a conversation if the platform has no such field.
3. To make it apply to every conversation by default, save it in whatever
   "always applied" settings area your platform offers (e.g. custom
   instructions, project/workspace instructions, a saved system prompt).
   Again — that opt-in step is done by you, in your own AI's settings, not
   by this skill automatically.

## Background

This is a public, cleaned-up evolution of a personal preview skill the
author uses day to day, extended to also flag knowledge-cutoff risk and to
formalize the prompt-optimization step, then generalized into
platform-neutral English so it can be reused anywhere.

## License

Licensed under the Apache License 2.0 — see [`LICENSE`](./LICENSE).
