<p align="center">
  <strong><code>EVOLVING AGENTS LABS</code></strong><br/>
  <sub>On-device adaptive AI. Six open-source experiments. Apache 2.0.</sub>
</p>

---

## Projects

### [skillos](https://github.com/EvolvingAgentsLabs/skillos) — markdown OS for AI agents

A pure markdown operating system. Define agents, tools, and memory as `.md` files — run them on Claude Code, Gemini CLI, or a 2B local model. Dream consolidation turns execution traces into reusable strategies overnight.

```bash
# Create and run agents from markdown
/skillos "Plan a weekly menu for 4 people"

# Dream consolidation — extract strategies from past runs
/skillos dream
```

### [skillos_plugin](https://github.com/EvolvingAgentsLabs/skillos_plugin) — Claude Code plugin for skillos

Install skillos as a Claude Code plugin. Adds the `/skillos` command — goal decomposition, agent creation, execution, trace logging, and memory consolidation in one prompt.

```bash
# Install
/plugin install /path/to/skillos_plugin/skillos-plugin

# Use
/skillos "Build a REST API with auth and tests"
```

### [skillos_systemcontrol_plugin](https://github.com/EvolvingAgentsLabs/skillos_systemcontrol_plugin) — governance for skillos projects

Control plane companion to skillos_plugin. Audits security, scores agents, proposes controlled improvements, and manages lifecycle (merge, deprecate, delete).

```bash
# Security scan
/sysctl "audit Project_webapp for vulnerabilities"

# Score and rank agents
/sysctl "score agents in Project_pipeline"

# Full maintenance pass
/sysctl "full maintenance on all projects"
```

### [skillos_mini](https://github.com/EvolvingAgentsLabs/skillos_mini) — on-device trade app (Android)

Capacitor + Svelte 5 Android app running Gemma 4 vision on-device via LiteRT. First vertical: a trade-app for tradespeople — capture a photo, get an AI diagnosis, generate a branded PDF, share via WhatsApp. No backend. Photos never leave the device.

```bash
# Dev server
npm run dev

# Build Android APK
npm run build && npx cap sync android
```

### [skillos_robot](https://github.com/EvolvingAgentsLabs/skillos_robot) — VLM-powered robot navigation

A 20cm cube robot (ESP32-S3 + stepper motors) driven by a vision language model. Give it a goal in plain language — it sees through the camera, reasons about the scene, and drives to the target. Failed runs get retried in MuJoCo simulation overnight.

```bash
# Navigate in simulation
robot navigate "go to the red cube"

# Navigate with local model (no internet)
robot navigate --local "go through the doorway"

# Dream — retry failed traces in simulation
robot dream
```

### [llm_os](https://github.com/EvolvingAgentsLabs/llm_os) — LLM as CPU

An operating system where the LLM is the CPU. 13-opcode ISA enforced by GBNF grammar at the sampler level — invalid sequences are physically impossible to emit. KV cache as RAM. Compaction as swap. Runs on a Raspberry Pi 5.

```bash
# Dev mode (Linux/macOS)
bash scripts/dev.sh --model models/qwen2.5-0.5b-q4.gguf

# Build bootable SD card image (Pi 5)
bash image/build.sh --model models/qwen2.5-3b-q4.gguf
```

---

<sub>Apache 2.0 · permanently alpha · 2026</sub>
