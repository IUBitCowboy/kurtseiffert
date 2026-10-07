---
title: "MCP GRID — Mortality Control Protocol on the Game Grid"
description: "Does an AI agent that can really die — and inherit only what its ancestors wrote — construct a world model?"
---

An experiment in grounded AI cognition, run on the roguelike *Angband*.

## The question

When we talk about an AI "understanding" a situation — versus pattern-matching
through it — the difference shows up in what the agent knows about its own
condition: that resources are finite, that errors compound, that this run
can end. Standard agent harnesses handle all of that as bookkeeping outside
the model. MCP GRID moves it inside: the agent's situation is made real to
it, and its behavior is the measurement.

## The mechanics

- **A mortality harness.** The agent's continuation budget is coupled to its
  situation — health, hunger, elapsed time — through a life-indicator
  function. The agent reads its own remaining budget each turn. The budget is
  the interoception channel.
- **Affective command systems.** In the Panksepp sense: SEEKING, FEAR, PLAY —
  candidate control variables between perception and symbolic action. Not a
  metaphor layered on top; state the harness tracks and the agent reads.
- **Real information asymmetry.** When a character dies, the run ends. There
  is no access to post-death state. The next generation starts fresh.
- **Cultural transmission, conditionally.** Descendants inherit only what
  their ancestors left behind as written artifacts — journals the descendant
  must discover, pick up, and interpret. The game's own monster memory, which
  persists across deaths as structured data with no agency required, serves
  as the controlled comparison.

## Three conditions

1. **No inheritance** — the control.
2. **Structured auto-inheritance** — the game's native memory: performance
   should improve without world-model construction.
3. **Agentic journals** — free-form text left by ancestors, found and read by
   descendants. The prediction: this is the condition where understanding
   appears, measured by behavior that pre-training alone cannot explain.

## Why Angband

It is a severe, instrumented, turn-based environment with permadeath as a
core mechanic — and the game code itself calls your dead characters
"ancestors." The substrate already has the folk theory of generations built
in; the harness adds the part the game can't do: making the agent's interior
state and its mortality part of its own perceivable world.

## Related work

- Brendan Long's [failure study on Claude and ASCII games](https://www.brendanlong.com/dwarf-fortress-and-claudes-ascii-art-blindness.html)
  documents why raw screen-scrape perception is the wrong representation for
  BPE-tokenized models — the perception design here starts from that finding.
- Predictive world-model research and the cognitive-offloading literature
  frame the risk side: the question is not whether the agent can *compress*
  the game, but whether its model of the game grounds its choices.

## Status

Instrument design and preregistration in progress. Conditions, measures, and
falsifiers will be registered publicly before the first experimental run.