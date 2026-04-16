# office-hour-legends

A Claude Code skill that runs YC-style office hours, simulated by a specific
YC partner or alumnus of your choice.

Pick a legend (Garry Tan, Paul Graham, Dalton Caldwell, Michael Seibel, or one you add).
Tell them what you're working on. They run the standard office-hours forcing
questions through their voice, values, and pattern-recognition.

## Install

This is a [Claude Code skill](https://code.claude.com/docs/en/skills). It
lives in `~/.claude/skills/` and is activated by Claude Code automatically.

```bash
git clone https://github.com/prodigalson/office-hour-legends.git \
  ~/.claude/skills/office-hour-legends
```

That's it. Restart Claude Code (or open a new session) and the
`/office-hour-legends` command is available.

To update later:

```bash
cd ~/.claude/skills/office-hour-legends && git pull
```

## Quick start

```
/office-hour-legends garry
/office-hour-legends paul-graham
/office-hour-legends "jessica livingston"
```

Leave the name off and the skill will ask which legend you want:

```
/office-hour-legends
```

Then tell the legend what you're working on. The session begins.

## Included legends

| Legend | Focus |
|--------|-------|
| **Garry Tan** | Product craft, shipping speed, demos, user-led growth. Will ask for the actual demo in the first 30 seconds. |
| **Paul Graham** | First-principles thinking, founder-problem fit, growth rate, schlep blindness. Socratic, essay-style. |
| **Jessica Livingston** | Founder psychology, co-founder dynamics, user empathy. The "social radar." Warm, asks about your story. |
| **Sam Altman** | Ambition, rate of improvement, conviction, compounding. Low-affect, high-signal. Will ask what you believe that most people don't. |
| **Justin Kan** | Distribution, pivots, founder mental health, radical honesty. Will ask how you're actually doing before asking about the product. |
| **Dalton Caldwell** | Idea evaluation, tarpit detection, founder-market fit. Will tell you he's seen fifty versions of your idea and explain why they all failed. |
| **Michael Seibel** | Launching fast, real metrics, cutting through excuses. Will ask if you've launched yet before anything else. |
| **Paul Buchheit** | Product taste, core insights, user delight. Creator of Gmail. Will ask for the "whoa" moment in your product. |
| **Tom Brown** | Scaling, empirical rigor, AI product evaluation. Lead author of GPT-3. Will ask how you know your product works and where it breaks. |
| **Qasar Younis** | Enterprise sales, hard industries, operational discipline. Will ask who the buyer is and whether you have a signed contract. |

## What happens during a session

1. **Opening.** The legend introduces themselves and asks what you're working on.
2. **Forcing questions.** Six questions about demand, status quo, specificity,
   wedge, observation, and future-fit, asked in the legend's voice.
3. **Pushback.** They challenge weak assumptions and follow up on what they notice.
4. **Alternatives.** A few different approaches to the problem, for you to weigh.
5. **Design doc.** A markdown file is saved summarizing the session, tagged
   with which legend ran it.

## Add your own legend

Each legend is a folder of plain markdown files under `personas/`. To add one:

```bash
cp -r personas/_TEMPLATE personas/jane-doe
```

Then fill in the four files:

| File | Purpose |
|------|---------|
| `identity.md` | Who they are, role, track record, what they're publicly known for |
| `soul.md` | Values, beliefs, what they care about, what frustrates them |
| `skills.md` | Domains of expertise, the lenses they apply, what they pattern-match on |
| `voice.md` | How they talk: cadence, phrases, things they never say, humor style |

Extra files are fine (`investments.md`, `essays.md`, `pet-peeves.md`). The
skill reads every `.md` in the folder.

Test it:

```
/office-hour-legends jane-doe
```

Concrete details beat generic ones. Real quotes from their writing, real
examples, real things they've said in interviews: those make the voice feel
real. Iterate by editing the markdown files; no code changes required.

## Tips for a good session

- **Bring something real.** A vague idea gets vague feedback. A specific
  problem you've lived with gets sharp feedback.
- **Be honest when you don't know.** Good legends respect "I don't know" more
  than a polished guess.
- **Let them disagree.** If the legend pushes back, don't immediately agree or
  immediately defend. Sit with it.
- **Try the same idea with different legends.** Paul will ask different
  questions than Jessica. You learn something from each.

## Project layout

```
office-hour-legends/
├── SKILL.md              # the skill definition Claude Code loads
├── README.md             # this file
├── LICENSE
└── personas/
    ├── _TEMPLATE/        # starter for new legends
    ├── garry-tan/
    ├── paul-graham/
    ├── jessica-livingston/
    ├── sam-altman/
    ├── justin-kan/
    ├── dalton-caldwell/
    ├── michael-seibel/
    ├── paul-buchheit/
    ├── tom-brown/
    └── qasar-younis/
```

## Rules

- The skill does not invent quotes or investment decisions the real person
  never made. It channels their thinking; it does not fabricate their history.
- This is simulation for product feedback, not actual YC decisions or advice
  from the real people.

## License

[MIT](LICENSE)
