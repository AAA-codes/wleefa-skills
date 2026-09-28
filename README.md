# Wleefa skills

Claude Code skills for the Wleefa team. Each skill is a folder at the root of this repo and installs as its own plugin from the `wleefa` marketplace.

| Folder | Plugin | What it does |
|---|---|---|
| `content-skill` | `content-skill@wleefa` | Write, edit, or audit Wleefa copy in the Wleefa voice, with the no-ai-slop writing rules built in |
| `motion-skill` | `motion-skill@wleefa` | Head of Motion Design: audit motion, demo options in the session, ship the picked option to staging |

## Install

One command, from any folder:

```bash
npx skills add AAA-codes/wleefa-skills -g
```

That installs every skill in this repo for the current user. Drop `-g` to install into the current project only, or pick one skill with `--skill wleefa-content`. Run the same command again to update.

Claude Code can also install it as a plugin:

```bash
claude plugin marketplace add AAA-codes/wleefa-skills
claude plugin install content-skill@wleefa
```

## Use in claude.ai

Writers on claude.ai cannot pull from GitHub. Upload the skill's `SKILL.md` (for content, `content-skill/skills/wleefa-content/SKILL.md`) as a skill in claude.ai under Settings, Capabilities, Skills, and re-upload it when the repo changes.

## Content skill

`content-skill/skills/wleefa-content/SKILL.md` holds what Wleefa is, the voice, terms, channel rules, approved examples, the no-ai-slop writing rules, and the check every draft passes before it is returned. In a session, `/wleefa-content` invokes it, and Claude also picks it up when a request mentions Wleefa copy.

Give it three things: the channel, the audience category, and what the reader should do afterwards. Then ask for new copy, paste a draft to edit, or paste a draft to check. Every result ends with a reminder that a human must approve the content before it is published.

The source of truth for the brand rules is the Wleefa Content Writer Guide deck (Google Slides, v1.0, September 2026). When the deck changes, update the SKILL.md and bump the version in `content-skill/.claude-plugin/plugin.json`.

## Motion skill

`motion-skill/skills/wleefa-motion/SKILL.md` holds the Wleefa motion feel (calm and premium), the motion tokens, the rules, and the demo-first process. In a session, `/wleefa-motion` invokes it, and Claude also picks it up when a request is about animation or interaction feel. It never ships motion the requester has not picked from a demo, and it logs every idea in `MOTION_LOG.md` in the website repo.

Owner: Abdulrahman Javaid. Approval: the marketing lead.
