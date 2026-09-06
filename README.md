---
title: Marketing Creative OS
tags: [marketing, creative-os]
updated: 2026-09-06
---

# Marketing Creative OS

Marketing Creative OS is an Obsidian knowledge base for turning brand knowledge, research, and performance learning into better marketing. It is designed to be useful to a nontechnical marketer: open the vault, ask a clear question, review the answer, and keep the approved learning.

This repository is public so the structure can be shared. Do not put secrets, private customer information, unreleased plans, or unlicensed assets in it.

## Start here

1. Open [[00-Home/Quickstart]].
2. Read [[01-Brand-Brain/MASTER-CONTEXT]].
3. Read [[01-Brand-Brain/Brand-Voice]], [[01-Brand-Brain/Visual-Identity]], and [[01-Brand-Brain/Claims-Whitelist]].
4. Open the relevant project in `13-Projects/`.
5. Before creating anything, ask an agent to search the vault and cite the notes it used.

For Nursery Pro, start with [[01-Brand-Brain/Nursery-Pro-Brand-Identity]], then read `13-Projects/Nursery-Pro/00-Project-Brief.md` and the project’s content, matrix, and creative-direction notes.

## The simple workflow

Use this loop for almost every request:

**search the vault → choose a goal → choose an audience → choose an angle → write a brief → create → review → approve → publish → record what was learned**

The vault stores the reasoning separately from the output. A renderer, image tool, or social platform can change without losing the brand strategy behind the work.

## Using the vault with Claude, Codex, or any CLI

You do not need to know a special command language. Give the agent the vault path and tell it to read the local rules first.

### Claude Code

```bash
cd /Users/macbookpro/Downloads/marketing-creative-os
claude
```

Then use a prompt such as:

> Work from this vault. Read `README.md`, `AGENTS.md`, `SKILL.md`, `01-Brand-Brain/MASTER-CONTEXT.md`, and the relevant project notes before answering. Search the vault first, cite the file paths you used, separate facts from suggestions, and do not invent claims.

### Codex CLI

```bash
cd /Users/macbookpro/Downloads/marketing-creative-os
codex
```

Use the same instruction. Codex can also edit notes when explicitly asked, but it must show the proposed change before a human approves it.

### Any other CLI or local agent

Point the tool at `/Users/macbookpro/Downloads/marketing-creative-os` and ask it to:

1. Read `README.md`, `AGENTS.md`, and `SKILL.md`.
2. Read `01-Brand-Brain/MASTER-CONTEXT.md`.
3. Search the relevant project, workflow, or skill notes.
4. Answer with links or file paths to its sources.
5. Mark unknowns and claims needing validation.

If the tool supports the Obsidian wiki commands, a targeted query can be written as:

```text
/wiki-query @marketing-creative-os What do we know about Nursery Pro's audience, voice, and approved claims?
```

If it does not support that command, use plain language:

> Search this vault for Nursery Pro audience, voice, and approved claims. Read the source notes, cite each file path, and tell me what is known, what is only a hypothesis, and what is missing.

## How to ask good questions

Include four things whenever possible:

- **Goal:** what decision or deliverable is needed;
- **Audience:** who will read or use it;
- **Channel or format:** landing page, Instagram post, carousel, reel, ad, email, or brief;
- **Constraints:** language, length, platform, deadline, approved claims, or assets available.

Ask the agent to distinguish **evidence**, **inspiration**, **community opinion**, and **new proposal**. Ask it to say “not found in the vault” instead of filling gaps with invented testimonials, statistics, customer numbers, certifications, or product capabilities.

## Copy-and-paste prompt library

### Query the vault

> Search this vault before answering: `[topic]`. Read `MASTER-CONTEXT.md` and the most relevant project notes. Return a short answer with cited file paths, then list contradictions, unknowns, and claims that need validation.

### Plan a campaign

> Use the campaign-strategy skill. Plan a campaign for `[product/project]` aimed at `[audience]` with the goal `[goal]` on `[channel]`. Read the brand context, content pillars, claims whitelist, and recent performance notes first. Return the audience insight, positioning, angle slate, formats, brief, measurement plan, and open questions. Do not invent proof.

### Create a static social post

> Use the social-static skill. Create three post directions for `[topic]` and `[audience]`. Follow the brand voice and visual identity in the vault. For each direction give the hook, body copy, CTA, visual concept, required asset, and claim check. Keep the alternatives meaningfully different.

### Create a carousel

> Use the carousel skill. Turn `[source idea or note]` into a `[number]`-slide carousel for `[platform]`. Cite the source notes, write one clear idea per slide, include the caption and CTA, and flag any slide that needs evidence or design review.

### Create a reel or short

> Use the reel skill. Create a `[duration]`-second concept for `[audience]` about `[topic]`. Include the first-second hook, shot list, on-screen text, voiceover, caption, CTA, and safe-to-claim notes. Keep the visual direction consistent with the project’s creative direction.

### Create UGC

> Use the UGC skill. Draft a creator brief for `[product/problem]` aimed at `[audience]`. Include the situation, talking points, proof the creator may use, do-not-say list, shot prompts, disclosure reminder, and approval checklist. Do not script a fake personal result.

### Create a paid ad

> Use the paid-ad skill. Build `[number]` ad variants for `[platform]` promoting `[offer]` to `[audience]`. Use only approved claims, write the primary text, headline, description, CTA, creative direction, landing-page message match, and experiment variable. Flag anything requiring legal or product validation.

### Repurpose an approved idea

> Use the repurpose skill. Start from `[approved note or asset]` and adapt it into `[formats/channels]`. Preserve the original insight and claim boundaries. Show what changes for each platform and what should remain consistent.

### Review creative

> Use the creative-review skill. Review `[file, copy, or URL]` against the brand voice, visual identity, audience, accessibility, platform fit, and claims whitelist. Classify findings as must fix, should fix, or polish. Give a precise correction for every finding and say what is already working.

### Review performance

> Use the performance-retro skill. Compare these results `[paste metrics or link to note]` with the campaign brief and previous learning. Separate signal from noise, identify likely causes, recommend the next test, and write the durable lesson that should be saved in `11-Performance/`. Do not overstate conclusions from a small sample.

### Add new research or source material

> Ingest this source into the vault: `[URL/file/text]`. First identify whether it is evidence, inspiration, community opinion, or an internal decision. Summarize only what the source supports, preserve the source link, connect it to relevant brand/project notes, and list follow-up questions. Do not overwrite existing knowledge silently.

## Main skills and workflows

The top-level router is [[SKILL]]. It tells an agent which specialist skill to use. The main skills are:

| Need | Use | Result |
| --- | --- | --- |
| Strategy or launch planning | `10-Agent-Skills/campaign-strategy/SKILL.md` | audience, angle, brief, channel plan, measurement |
| One static post | `10-Agent-Skills/social-static/SKILL.md` | platform-ready post direction and copy |
| Educational or narrative carousel | `10-Agent-Skills/carousel/SKILL.md` | slide-by-slide structure and caption |
| Short-form video | `10-Agent-Skills/reel/SKILL.md` | hook, shots, text, voiceover, CTA |
| Creator-led content | `10-Agent-Skills/ugc/SKILL.md` | creator brief with guardrails |
| Paid acquisition | `10-Agent-Skills/paid-ad/SKILL.md` | ad variants and test plan |
| Turn one idea into many outputs | `10-Agent-Skills/repurpose/SKILL.md` | channel-specific adaptations |
| Quality and brand check | `10-Agent-Skills/creative-review/SKILL.md` | prioritized critique and corrections |
| Learn from results | `10-Agent-Skills/performance-retro/SKILL.md` | evidence-based retro and next test |

The repeatable agent roles in `09-Agent-Workflows/` explain how to combine these skills:

- **Scout** finds useful evidence and references.
- **Planner** turns a goal into an actionable brief.
- **Copy Agent** writes within the voice and claim boundaries.
- **Visual Agent** turns the approved idea into a visual direction.
- **Reviewer** checks quality, accessibility, and platform fit.
- **Human Approval** records the decision before publication.
- **Analyst** and **Performance Learning Loop** turn results into reusable knowledge.

Always load the brand context first. Never let an image or copy generator decide the strategy by default.

## Where things live

- `01-Brand-Brain/` — voice, visual identity, product truths, claims, and approved assets;
- `02-Product-Marketing/` — audiences, objections, product positioning, and proof;
- `03-Content-Strategy/` — campaigns, pillars, and planning;
- `04-Hooks-Angles/` — opening lines and creative territories;
- `05-Formats/` — briefs for posts, reels, carousels, ads, and testimonials;
- `06-Platforms/` — platform-specific guidance;
- `07-Creative-Direction/` — visual rules and review standards;
- `08-Swipe-File/` — references worth studying;
- `09-Agent-Workflows/` — repeatable ways to work with agents;
- `10-Agent-Skills/` — specialist skills;
- `11-Performance/` — results and lessons;
- `12-Research/` — source material waiting to be distilled;
- `13-Projects/` — project-specific marketing work;
- `Templates/` — reusable briefs and review checklists.

## Approval and safety rules

Drafting and reviewing can be assisted. Publishing, spending money, changing public claims, and using customer or child-related information still require a human decision.

Before approving work, check:

- Is the audience and desired action clear?
- Is every factual claim supported by the vault or marked for validation?
- Are imagery, logos, quotes, and music licensed or approved?
- Is the language accessible and appropriate for the platform?
- Has someone reviewed the final creative at the actual mobile size?

## After a session

1. Review the agent’s file changes and remove anything speculative.
2. Ask for a short summary of decisions, open questions, and sources used.
3. Save durable learning in the correct folder, especially `11-Performance/`.
4. Run a vault check if available:

   ```bash
   PYTHONPATH=/Users/macbookpro/Documents/tools/obsidian-wiki \
   python3 -m obsidian_wiki.cli doctor \
   --vault /Users/macbookpro/Downloads/marketing-creative-os
   ```

5. Sync only after review:

   ```bash
   PYTHONPATH=/Users/macbookpro/Documents/tools/obsidian-wiki \
   python3 -m obsidian_wiki.cli sync \
   --vault /Users/macbookpro/Downloads/marketing-creative-os
   ```

If the wiki tool is not installed, simply review the Markdown diff and commit it with Git after approval.

## Nursery Pro note

Nursery Pro material lives in `13-Projects/Nursery-Pro/`. Its brand assets and logo references are in [[01-Brand-Brain/Nursery-Pro-Brand-Identity]]. The current mobile app icon and Eggy artwork are identified there, and the older logo with hands and legs is preserved as a legacy reference. Use the project claims and product notes before writing public-facing copy.

## Backup and contribution

This vault is hosted publicly at [Atou4/marketing-creative-os](https://github.com/Atou4/marketing-creative-os). Keep secrets, private customer information, and unlicensed assets out of the repository. Prefer small, reviewable changes with a clear note explaining what was learned or decided.
