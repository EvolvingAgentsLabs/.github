<p align="center">
  <strong><code>EVOLVING AGENTS LABS</code></strong><br/>
  <sub>Agents defined in markdown. Evolved through memory. Running from Claude Code to bare metal.</sub>
</p>

---

One thesis explored at five levels of depth: agent behavior belongs in declarative documents, the LLM is the interpreter, memory is how agents improve, and grammar/structure is how you keep them safe.

Each layer removes a safety net. Each one proves the same patterns work at increasing depth.

```
                         ┌───────────────┐
                         │    llm_os     │  LLM is the CPU. 14-opcode ISA.
                         │    (Rust)     │  GBNF grammar = type system.
                     ┌───┴───────────────┴───┐
                     │     skillos_robot      │  VLM-driven robot. $30 hardware.
                     │     (TypeScript)       │  Dream consolidation.
                 ┌───┴───────────────────────┴───┐
                 │        skillos_mini            │  On-device. 2B model. No internet.
                 │        (Svelte/Capacitor)      │  Deterministic safety checks.
             ┌───┴───────────────────────────────┴───┐
             │              skillos                    │  Full markdown OS. Any LLM.
             │              (Pure Markdown)            │  Memory + evolution + planning.
         ┌───┴───────────────────────────────────────┴───┐
         │     skillos_plugin + skillos_systemcontrol      │  Try it now in Claude Code.
         │     (Claude Code plugins)                       │  Install in 10 seconds.
         └─────────────────────────────────────────────────┘
```

---

## Start here — try in 30 seconds

### [skillos_plugin](https://github.com/EvolvingAgentsLabs/skillos_plugin) + [skillos_systemcontrol_plugin](https://github.com/EvolvingAgentsLabs/skillos_systemcontrol_plugin)

The fastest way to explore SkillOS concepts. Install in Claude Code, give it a goal — it creates agents, executes them, and consolidates learnings. `/sysctl` governs what `/skillos` builds.

```bash
/skillos "Build a REST API with auth and tests"
# → 3 agents created, triad decomposition, output in projects/

/sysctl "audit and score all agents"
# → security scan, performance scores, evolution proposals
```

---

## Full system — markdown-defined agent OS

### [skillos](https://github.com/EvolvingAgentsLabs/skillos) — Pure Markdown Operating System

Every component — agents, tools, memory, orchestration — defined in `.md` files interpreted by any LLM at runtime. HWM hierarchical planning, 14 token-compression dialects, dream consolidation, self-optimization. Runs on Claude, Gemini, Gemma 4, or any OpenAI-compatible endpoint.

```bash
skillos execute: "Run the Operation Echo-Q scenario"
# → 4 agents, 5 wiki pages, working quantum_cepstrum.py
```

---

## On-device — same concepts on a phone

### [skillos_mini](https://github.com/EvolvingAgentsLabs/skillos_mini) — On-device trade assistant (Android)

Markdown cartridges guide a 2B local LLM through trade diagnostics. Electrician (IEC 60364), plumber, painter. All safety rules execute as deterministic TypeScript functions. No internet required. Gemma 4 on-device via LiteRT.

```bash
# "panel has exposed wiring and no RCD"
# → route: electricista → checkWireGauge → FALLA → checkRCD → PELIGRO
# → diagnosis: Recableado 4mm² + diferencial 30mA
```

---

## Real world — embodied cognition for $30

### [skillos_robot](https://github.com/EvolvingAgentsLabs/skillos_robot) — VLM-powered robot navigation

A 20cm robot driven by a vision language model. Give it a goal — it sees through the camera, reasons about the scene, and drives to the target. Failed traces get retried in MuJoCo simulation during dream consolidation.

```bash
robot navigate "go to the red cube"
# → VLM perception at 1-2 Hz, motor control at 10-20 Hz
# → target reached in 12 steps

robot dream
# → 3 failed traces retried in simulation → new strategies
```

---

## Bare metal — the LLM is the CPU

### [llm_os](https://github.com/EvolvingAgentsLabs/llm_os) — An OS where the LLM is the CPU

14-opcode ISA enforced by GBNF grammar at decode time — invalid sequences are physically impossible to emit. In-process inference via Rust FFI to llama.cpp. KV cache as RAM with deterministic paging. WASM-sandboxed cartridges. Boots from SD card on a Raspberry Pi 5 at 8 Hz.

```bash
bash scripts/dev.sh --model qwen2.5-3b-q4.gguf
# → in-process FFI, grammar stack, 6 cartridges mounted

bash image/build.sh --model qwen2.5-3b-q4.gguf
# → pi5-sdcard.img (1.8GB, boots to iod)
```

---

<sub>Apache 2.0 · permanently alpha · 2026 · <a href="https://evolvingagentslabs.github.io">evolvingagentslabs.github.io</a></sub>
