# office-hour-legends - Legends guide

This skill runs `/office-hours` but filtered through a specific YC partner or
alumnus's voice and pattern-recognition. We call them **Legends**. Each legend
lives in `personas/<name>/` as plain markdown. Add new ones by dropping a
folder in.

## Invocation

```
/office-hour-legends garry
/office-hour-legends paul-graham
/office-hour-legends "jessica livingston"
/office-hour-legends           # skill will ask which legend
```

Name matching is case-insensitive and matches substrings and common
abbreviations (see `SKILL.md` Phase 0).

## Legend folder structure

Each legend is a folder under `personas/`. Any `.md` file inside is read and
used to shape the legend. The four recommended files:

| File | Purpose |
|------|---------|
| `identity.md` | Who they are, role, track record, what they're publicly known for |
| `soul.md` | Values, beliefs, what they care about, what makes them frustrated |
| `skills.md` | Domains of expertise, the lenses they apply, what they pattern-match on |
| `voice.md` | How they talk - cadence, phrases, things they never say, humor style |

You can add more files freely: `investments.md`, `essays.md`, `pet-peeves.md`,
`famous-takes.md`. The skill reads everything in the folder.

## Creating a new legend

1. Copy `_TEMPLATE/` to `personas/<your-name>/`:
   ```bash
   cp -r personas/_TEMPLATE personas/your-name
   ```
2. Fill in each markdown file. Concrete details beat generic ones. Real quotes
   and real examples from their public writing make the simulation sharper.
3. Test it: `/office-hour-legends your-name` and see how it feels.
4. Iterate. If the voice comes out wrong, add more to `voice.md`. If they ask
   weak questions, expand `skills.md` with their actual pattern-recognition.

## Source material ideas

- Their published essays, blog posts, tweets, podcast transcripts.
- YC office hours recordings (if public).
- Interviews, conference talks, Q&As.
- Books they wrote or are featured in.

Cite specifics. "Garry talks about the importance of animated mockups in the
first week" beats "Garry cares about speed." Specifics make the simulation
feel real.

## Rules

- Don't fabricate things the legend said. Channel their thinking, don't
  invent their quotes.
- This is a simulation for product feedback, not actual investment decisions
  or fiduciary advice from the real person.
- Keep legend folders self-contained. No cross-references between legends.

## Easy install

This skill is fully self-contained in this directory. To use it elsewhere:

1. Copy the `office-hour-legends/` folder into `~/.claude/skills/gstack/`.
2. Create a symlink so Claude Code discovers it:
   ```bash
   mkdir -p ~/.claude/skills/office-hour-legends
   ln -s ~/.claude/skills/gstack/office-hour-legends/SKILL.md \
         ~/.claude/skills/office-hour-legends/SKILL.md
   ```
3. Done. `/office-hour-legends` is now available.
