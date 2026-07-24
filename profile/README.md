<p align="center">
  <strong><code>EVOLVING AGENTS LABS</code></strong><br/>
  <sub>Experiments in how agents learn, remember, and prove what they know.</sub>
</p>

---

Agents that modify themselves are easy to build and hard to trust. Everything here attacks the second half of that sentence — versioning an agent's evolution so a human can review it, reading a model's internal workspace to catch a memory it was tricked into keeping, or constraining a small model at the decoder so invalid output is not discouraged but impossible.

Each experiment is labelled by how much evidence stands behind it — including the ones where the evidence went against us.

| Badge | Means |
|---|---|
| **Reproducible** | clone it and run it, no API key |
| **Results** | published findings, negative ones included |
| **Prototype** | runs, but needs setup or has no eval yet |

---

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
pip install agentvcs
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

### [evolving-memory](https://github.com/EvolvingAgentsLabs/evolving-memory) — **Results** · Apr 2026

*What if an agent's memory consolidated itself the way sleep consolidates yours?*

A trajectory engine that chunks execution traces, connects them and curates what survives, so repeated experience raises confidence and failures extract constraints — without one domain's lessons bleeding into another.

---

<sub>Apache 2.0 · permanently alpha · <a href="https://evolvingagentslabs.github.io">evolvingagentslabs.github.io</a></sub>
