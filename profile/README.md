<p align="center">
  <strong><code>EVOLVING AGENTS LABS</code></strong><br/>
  <sub>Experiments in how agents learn, remember, and prove what they know.</sub>
</p>

---

**By [Matias Molinas](https://github.com/matiasmolinas) and [Ismael Faro](https://github.com/ismaelfaro)** — the ideas, the architecture and the code, out of an ongoing conversation between the two. The repositories are where those conversations get tested.

Agents that modify themselves are easy to build and hard to trust. Everything here attacks the second half of that sentence — versioning an agent's evolution so a human can review it, reading a model's internal workspace to catch a memory it was tricked into keeping, or constraining a small model at the decoder so invalid output is not discouraged but impossible.

Each experiment is labelled by how much evidence stands behind it — including the ones where the evidence went against us.

| Badge | Means |
|---|---|
| **Reproducible** | clone it and run it, no API key |
| **Results** | published findings, negative ones included |
| **Prototype** | runs, but needs setup or has no eval yet |

---

### [gene-evidence](https://github.com/EvolvingAgentsLabs/gene-evidence) — **Prototype** · Oct 2026

*What if every sentence in a gene report could be traced back to the tool output it rests on?*

Evidence reports for predicted protein-coding genes that the reference annotation does not have: locus context, retrocopy signature, Swiss-Prot homology, Pfam domains, ORF sanity and optional RNA support, collected into an evidence graph and rendered as a report in which every sentence cites the nodes it rests on. Deterministic — two independent runs produce byte-identical output — and with no LLM in stage 1. It does not claim that its ranking finds real genes.

### [sleep-harness](https://github.com/EvolvingAgentsLabs/sleep-harness) — **Results** · Jul 2026

*What if you could catch a poisoned memory by watching which concepts light up inside the model?*

An interpretability firewall for agent memory. Reads the residual stream through a Jacobian lens to flag injected instructions that are lexically identical to benign text, and to scan third-party adapters for trojans before they mount. Hypotheses are pre-registered; the refuted ones are published alongside the confirmed ones.

### [evolving-robot](https://github.com/EvolvingAgentsLabs/evolving-robot) — **Prototype** · Jul 2026

*What if a robot that missed a fallen patient could rewrite its own care protocol overnight?*

Florence patrols a hospital ward, fails to check a patient standing outside her lamp radius, and revises the skill that caused it. The rewrite survives only if it outscores the protocol it replaced; otherwise it is reverted, with the reason on a durable ledger.

### [agentvcs](https://github.com/EvolvingAgentsLabs/agentvcs) — **Reproducible** · Jul 2026

*What if an agent's autonomous evolution could be merged back into your release, like any other branch?*

Version control where one commit carries code, goal, model pins, trace and sub-agent swarm together. Conflicts between what the agent taught itself at runtime and what your team edited in git are handed to a reconciler over a plain stdin/stdout contract.

```bash
git clone https://github.com/EvolvingAgentsLabs/agentvcs
cd agentvcs && pip install -e .
bash examples/eve-evolve-merge/demo.sh   # runs offline, no API key
```

### [qa](https://github.com/EvolvingAgentsLabs/qa) — **Prototype** · Jun 2026

*What if your test suite told you what it had quietly stopped checking?*

Every assertion is fingerprinted and diffed across runs, so a check that silently disappeared surfaces as a finding. Exploratory browser sessions that pass get frozen into deterministic scripts; steps that failed become explicit skips rather than silence.

### [skillos](https://github.com/EvolvingAgentsLabs/skillos) — **Prototype** · Jun 2026

*What if the operating system were written entirely in markdown?*

Skills as programs, traces as logs, consolidation as sleep. Includes a line-op dialect that lets small models patch files by emitting edits instead of rewriting whole documents, measured by an AST-verified benchmark rather than an LLM judge.

### [token-trie](https://github.com/EvolvingAgentsLabs/token-trie) — **Reproducible** · May 2026

*What if a small model could not emit invalid syntax, because the decoder refused to let it?*

Every legal instruction is pre-tokenized into a trie of token IDs, and the sampler's valid-next set is masked at each step. A 350M-parameter model plays Tetris in a browser tab, fully offline. Grammar enforced in the decoder, not requested in the prompt.

### [skillos_robot](https://github.com/EvolvingAgentsLabs/skillos_robot) — **Prototype** · May 2026

*What if the robot were just a device driver for a language model?*

A slow vision-language brain plans at roughly one hertz while a reactive controller drives motors at twenty, over a bytecode link to an ESP32. Firmware, CAD and simulation scenes included.

### [evolving-agents](https://github.com/EvolvingAgentsLabs/evolving-agents) — *where this came from* · 2025

*What if the decomposition was right and the substrate was wrong?*

The Evolving Agents Toolkit: eighteen thousand lines describing five subsystems, and
three test functions. Each subsystem was independently rebuilt over the following year
on something that could be tested. Its `firmware.py` sets a governance string asking a
model to "never use dangerous imports"; token-trie makes the token unreachable. Same
intention, one substrate apart — the code is still there so you can diff it.

### [evolving-memory](https://github.com/EvolvingAgentsLabs/evolving-memory) — **Results** · Apr 2026

*What if an agent's memory consolidated itself the way sleep consolidates yours?*

A trajectory engine that chunks execution traces, connects them and curates what survives, so repeated experience raises confidence and failures extract constraints — without one domain's lessons bleeding into another.

---

## The through-line

Nine experiments, one question: not whether an agent can do something, but how you
would know it did. Three mechanisms kept working, and they turned up independently
before they looked like the same idea.

**Constrain the mechanism, not the prompt.** Masking the sampler's valid-next set makes
malformed output unreachable. The matched negative is what makes it convincing: the
prompt-level version of the same objective fires in 1 of 7 identical sessions, and
instructing harder measured worse.

**Prove it, then freeze it.** Run the expensive non-deterministic thing once, verify it,
crystallize it into something replayable — enforced in code, not in a README.

**Look where the standard filter is blind.** A keyword filter over agent memory cannot
see a payload written in words it likes; a coverage tool cannot see the check you
stopped making.

And the half that makes the rest worth reading: a pre-registered founding hypothesis
marked **REFUTADA**, and a published retraction of a claim that came from n=1 and
reversed on re-run.

**[Read the full thesis →](https://evolvingagentslabs.github.io/thesis/)**

---

<sub>Apache 2.0 · permanently alpha · <a href="https://evolvingagentslabs.github.io">evolvingagentslabs.github.io</a></sub>
