# persuasion

**Your agent writes copy. This skill makes it reason about why people say yes.**

A persuasion skill for Claude Code, Cursor, Codex, OpenCode, and 16 other agents. It reads
the decision in front of you, picks the lever that fits it, and writes the pitch, offer, or
message. Every recommendation names the mechanism behind it.

```bash
npx skills add atpaawej/persuasion
```

Installs into your agent's skill directory in about ten seconds. It's a Markdown folder, so
there is nothing to configure.

Listed on [skills.sh](https://www.skills.sh/atpaawej/persuasion/persuasion), where it passes
the Gen Agent Trust Hub, Socket, and Snyk security audits.

## What changes

| A generic agent writes | With `persuasion` loaded |
| --- | --- |
| "Unlock your team's potential with powerful analytics." | "You rebuild the Monday report by hand every week. That's 90 minutes you don't get back." |
| "Our solution helps teams save time." | "The status quo is free, so the paid tier reads as a loss. Frame it as what the free tier costs them." |
| "Add urgency to increase conversions." | "The deadline is real, so state the date. An invented one fails the test." |

Same model. The difference is that the second column knows what it is doing to a person.

## Ask it things like

| Ask | What comes back |
| --- | --- |
| "This landing page isn't converting." | The reference point, the frame that fits, and the rewritten copy |
| "Write a pitch for our seed round." | A five-beat story with the strongest objection answered |
| "Why won't my team adopt this tool?" | The load, the prior belief, and the loss they are protecting |
| "How should I price the pro tier?" | Anchoring and a 2–3 option set built against the status quo |
| "Is this countdown timer ethical?" | Green or red, plus the honest replacement if it's red |
| "Handle the 'too expensive' objection." | The real objection, answered in the buyer's own words |

## What you get back

1. **Diagnosis.** The decision, the status quo, the cognitive load, the prior belief, and
   what the audience stands to lose.
2. **The lever.** Framing, fluency, social proof, or narrative, with the reason it follows
   from the diagnosis.
3. **The artifact.** The copy, the offer, the script, or the pricing page change itself.
4. **The mechanism.** One paragraph on why this works on this audience.
5. **The test result.** Green, or the red and its replacement.

The science stays in the reasoning. The deliverable is the email, not an essay about
Kahneman.

## Inside

`SKILL.md` runs a four-step loop: map the decision, route to one lever, build the argument,
run the disclosure test. Reference modules load only when the map sends the agent there, so
you pay for the module you need and nothing else.

| Module | Covers |
| --- | --- |
| [cognitive-architecture](references/cognitive-architecture.md) | Bounded rationality, System 1 and System 2, cognitive load, choice architecture |
| [framing-and-loss-aversion](references/framing-and-loss-aversion.md) | Prospect theory, the loss multiplier, the fourfold pattern, anchoring, endowment |
| [influence-levers](references/influence-levers.md) | Reciprocity, commitment, social proof, authority, liking, scarcity, unity, key biases |
| [narrative](references/narrative.md) | Narrative transportation, the Sparkline and Hero's Guide arcs, self-referential encoding |
| [ethics](references/ethics.md) | The manipulation spectrum, the disclosure test, the automatic reds |

## It checks itself before it hands you the draft

> If the audience read an accurate, plain-language explanation of the mechanism being used,
> would they still willingly proceed?

A no means the tactic gets replaced, not reworded. Fabricated proof, invented deadlines,
hidden fees, and obstructed cancellation are treated as failures, even when they would test
well.

## Manual install

```bash
git clone https://github.com/atpaawej/persuasion.git ~/.claude/skills/persuasion
```

| Agent | Path |
| --- | --- |
| Claude Code | `~/.claude/skills/persuasion` |
| OpenCode | `~/.config/opencode/skills/persuasion` |
| Project-local | `.claude/skills/persuasion` (or your agent's equivalent) |

Keep the folder named `persuasion` so it matches the `name` in `SKILL.md`.

## Questions

**Does it work with my agent?** The `npx skills` CLI detects installed agents and writes to
each one. Twenty are supported:

<details>
<summary>Supported agents</summary>

Claude Code · Cursor · Codex · GitHub Copilot · Windsurf · Gemini · Cline · AMP ·
Antigravity · OpenClaw · Droid · Goose · Kilo · Kiro CLI · Nous Research · OpenCode · Roo ·
Trae · VS Code · Zed

</details>

**Will it make my agent sound like a late-night sales page?** Its first rule is that every
recommendation names a mechanism, and its last step rejects anything that only works because
the audience doesn't know it's being used.

**Can I edit it?** It's five Markdown files. Change a reference, run the command again.

## License

MIT. See [LICENSE](LICENSE).
