# Legends - Simple Documentation

Run a YC office hours session with a simulated YC partner or alumnus of your
choice. Same forcing questions as `/office-hours`, but in their voice, through
their lens.

## What it does

You have a startup idea or a project you want to pressure-test. Normally you'd
run `/office-hours` to get the standard six forcing questions. With Legends,
you pick **who** runs the session - Garry Tan, Paul Graham, Jessica Livingston,
or anyone else you add.

Each legend asks different questions, notices different things, and gives
advice in their own voice.

## Quick start

Just type the command and a name:

```
/office-hour-legends garry
/office-hour-legends paul-graham
/office-hour-legends "jessica livingston"
```

If you leave the name off, the skill will ask you who you want.

```
/office-hour-legends
```

Then tell the legend what you're working on, and the session begins.

## Who's already included

| Legend | What they focus on |
|--------|-------------------|
| **Garry Tan** | Product craft, shipping speed, demos, user-led growth. Will ask for the actual demo in the first 30 seconds. |
| **Paul Graham** | First-principles thinking, founder-problem fit, growth rate, schlep blindness. Socratic, essay-style. |
| **Jessica Livingston** | Founder psychology, co-founder dynamics, user empathy. The "social radar." Warm, asks about your story. |

## Adding your own legend

Each legend is a folder of plain markdown files. To add one:

1. Go to `~/.claude/skills/gstack/office-hour-legends/personas/`
2. Copy `_TEMPLATE/` and rename it to the new person's name (use hyphens, no
   spaces - e.g. `jane-doe`).
3. Fill in the four files inside:
   - **identity.md** - who they are, what they're known for
   - **soul.md** - what they believe, what they care about, what frustrates them
   - **skills.md** - what they're expert at, what lenses they apply
   - **voice.md** - how they actually talk, phrases they use, things they never say
4. Try it: `/office-hour-legends jane-doe`

The more specific you are in those files, the more convincing the simulation.
Real quotes from their writing, real examples, real things they've said in
interviews - those make the voice feel real.

## What happens during a session

1. **Opening.** The legend introduces themselves briefly and asks what you're
   working on.
2. **Forcing questions.** For startup ideas, six questions about demand,
   status quo, specificity, wedge, observation, and future-fit - asked in
   the legend's voice.
3. **Pushback.** The legend challenges weak assumptions, asks follow-ups based
   on what they notice.
4. **Alternatives.** The skill generates a few different approaches to the
   problem for you to weigh.
5. **Design doc.** A markdown file saved with a summary of the session,
   including which legend ran it.

## Tips for a good session

- **Bring something real.** A vague idea gets vague feedback. A specific
  problem you've lived with gets sharp feedback.
- **Be honest when you don't know.** Legends (the good ones) respect "I don't
  know" more than a polished guess.
- **Let them disagree with you.** If the legend pushes back, don't immediately
  agree or immediately defend. Sit with it.
- **Try the same idea with different legends.** Paul will ask different
  questions than Jessica. You learn something from each.

## Easy install

This skill is self-contained. To install it elsewhere:

1. Copy the `office-hour-legends/` folder into `~/.claude/skills/gstack/`.
2. Make a symlink so Claude Code can find it:
   ```bash
   mkdir -p ~/.claude/skills/office-hour-legends
   ln -s ~/.claude/skills/gstack/office-hour-legends/SKILL.md \
         ~/.claude/skills/office-hour-legends/SKILL.md
   ```
3. `/office-hour-legends` is now available.

## Rules

- The skill doesn't invent quotes or investment decisions the real person
  never made. It channels their thinking; it doesn't fabricate their history.
- This is simulation for product feedback, not actual YC decisions or advice
  from the real people.
- Persona files are plain markdown. You can edit them anytime to refine the
  simulation.

## Where things live

```
~/.claude/skills/gstack/office-hour-legends/
├── SKILL.md          # the skill itself
├── README.md         # contributor guide
├── DOCS.md           # this file
└── personas/
    ├── _TEMPLATE/    # starter template for new legends
    ├── garry-tan/
    ├── paul-graham/
    └── jessica-livingston/
```

That's it. Pick a legend, start a session, take notes.
