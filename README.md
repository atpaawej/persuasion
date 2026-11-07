# persuasion

An agent skill for persuasion built on cognitive psychology and behavioral economics. It
diagnoses why an audience resists, picks the lever the diagnosis points at, and writes the
pitch, offer, or message — with the mechanism named and the ethics checked.

No sales scripts, no urgency tricks. Every recommendation comes with the reason it works on
this audience.

## Install

```bash
npx skills add atpaawej/persuasion
```

The [skills](https://skills.sh) CLI detects your agent — Claude Code, Cursor, Codex,
OpenCode, Copilot, Gemini, and the rest — and installs to the right directory.

**Manual install** (any agent, anywhere):

```bash
git clone https://github.com/atpaawej/persuasion.git ~/.claude/skills/persuasion
```

Common skill directories:

| Agent | Path |
| --- | --- |
| Claude Code | `~/.claude/skills/persuasion` |
| OpenCode | `~/.config/opencode/skills/persuasion` |
| Project-local | `.claude/skills/persuasion` (or your agent's equivalent) |

The folder name must stay `persuasion` — it has to match the `name` in `SKILL.md`.

## Usage

The skill fires on its own when a request matches. You can also name it:

```
Use the persuasion skill to rewrite this pricing page.
```

Things it handles:

| Ask | What you get |
| --- | --- |
| "This landing page isn't converting." | The reference point, the frame to use, and the rewritten copy |
| "Write a pitch for our seed round." | A five-beat story with the objection answered |
| "Why won't my team adopt this tool?" | A diagnosis of the load, the prior, and the loss |
| "How should I price the pro tier?" | Anchoring and option-set design against the status quo |
| "Is this countdown timer ethical?" | A green/red result and the replacement if it's red |
| "Handle the 'too expensive' objection." | The strongest real objection, answered in the audience's terms |

## What comes back

Every run returns five things:

1. **Diagnosis** — the decision, the status quo, the cognitive load, the prior belief, and
   what the audience stands to lose.
2. **The lever** — framing, fluency, social proof, narrative, or a combination, with why.
3. **The artifact** — the copy, the offer, the script, or the page change itself.
4. **The mechanism** — one paragraph on why it works on this audience.
5. **The disclosure test** — green, or the red and its replacement.

## How it works

`SKILL.md` runs a four-step loop:

1. **Map the decision** — name the choice, the status quo, the load, the prior, the loss.
2. **Route to the lever** — one reference module, chosen by the map, not by preference.
3. **Build the argument** — frame, reference point, 2–3 options, one story, the real
   objection answered.
4. **Run the disclosure test** — would the audience still say yes if they knew the mechanism?

Reference modules load only when the routing table sends the agent there:

| Module | Covers |
| --- | --- |
| [cognitive-architecture](references/cognitive-architecture.md) | Bounded rationality, System 1 / System 2, cognitive load, choice architecture |
| [framing-and-loss-aversion](references/framing-and-loss-aversion.md) | Prospect theory, the loss multiplier, the fourfold pattern, anchoring, endowment |
| [influence-levers](references/influence-levers.md) | Reciprocity, commitment, social proof, authority, liking, scarcity, unity, key biases |
| [narrative](references/narrative.md) | Narrative transportation, the Sparkline and Hero's Guide arcs, self-referential encoding |
| [ethics](references/ethics.md) | The manipulation spectrum, the disclosure test, the automatic reds |

Progressive disclosure keeps the always-loaded cost to the name and description; the body
loads on activation, the modules only when reached.

## Ethics

The skill runs a disclosure test on everything it produces:

> If the audience read an accurate, plain-language explanation of the mechanism being used,
> would they still willingly proceed?

If the answer is no, it says so and offers the honest version that reaches the same goal.
Fabricated proof, invented deadlines, hidden fees, and obstructed cancellation are treated
as automatic failures, not tactics.

## Structure

```
persuasion/
├── SKILL.md
├── references/
│   ├── cognitive-architecture.md
│   ├── framing-and-loss-aversion.md
│   ├── influence-levers.md
│   ├── narrative.md
│   └── ethics.md
└── source/
    └── persuasion-first-principles-skill.md
```

`SKILL.md` follows the [Agent Skills](https://agentskills.io) specification: YAML frontmatter
with `name` and `description`, instructions in the body, reference files one level deep.

## Contributing

Issues and PRs welcome. Keep `SKILL.md` under 500 lines, push branch-specific material into
`references/`, and name the mechanism behind any advice you add.

## License

MIT — see [LICENSE](LICENSE).
