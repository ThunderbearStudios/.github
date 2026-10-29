# Thunderbear Studios™ — Independent Software & Applied-AI Engineering Studio

We build deterministic verification and memory tools for AI coding assistants, 64-bit multi-track audio DSP software, and real-time 60fps WebGL2/C/C++ applications.

- **Studio & Technical Overview:** [thunderbearstudios.org](https://thunderbearstudios.org) ([Technical Overview](https://thunderbearstudios.org/diligence/) · [Published Literature & Standards Mapping](https://thunderbearstudios.org/research/))
- **Resonant MCP (v2.5):** [resonantexo.com](https://resonantexo.com) (`https://resonantexo.com/api/mcp`) — Sub-2ms pre-save code verification, OASIS SARIF v2.1.0 CI/CD gate & AST-linked memory (`2025-03-26` MCP spec)
- **Angband 3D (v11.1.1):** [angband3d.com](https://angband3d.com) — Live 60fps Three.js/WebGL2, Desktop C# & Android proving ground ([ThunderbearStudios/angband3d](https://github.com/ThunderbearStudios/angband3d))
- **Contact:** `founder@thunderbearstudios.org` / `dev@thunderbearstudios.org`

---

## Active Systems (Public Sandbox & Early Access — Pre-Revenue)

### 1. [Resonant MCP](https://resonantexo.com) & Resonant Cloud (`v2.5`)
AI coding assistants frequently edit files using outdated context, break callers across modules, or introduce security/runtime regressions. **Resonant MCP** exposes a zero-dependency Python verification and memory engine (`tb_cs_engine.py`, 31/31 engine tests & 103/103 cloud backend tests passing) over the Model Context Protocol (`2025-03-26` spec, 7 annotated tools, 3 prompts, 3 resources, `<2 ms` per verification call, 0 LLM tokens per verification call):

- **Pre-Save Contract & Bytecode Verification (`resonant_verify_cegar`):** Diffs old vs. new function contracts, runs restricted Python bytecode across boundary inputs, checks 10 CWE classes and 60fps render-loop rules, and emits JSON or OASIS SARIF v2.1.0 reports before save.
- **Surgical Call-Graph & Git Co-Change Slicing (`resonant_architect_orient`):** Extracts target function contracts, shared-state callers, and historical Git co-change partners (~87% context token reduction).
- **AST-Linked Project Memory (`resonant_memory_jtms`):** Binds architectural notes to normalized AST SHA-256 fingerprints so stale notes automatically transition to `STALE_AST_DRIFT` when code changes.
- **0-Token Structural Guardrails (`resonant_evolve_guardrail`) & Completion Auditing (`resonant_honesty_audit`).**
- **Google Cloud Run Backend:** Hosted on Google Cloud Run (`us-central1`) with Cloud Storage FUSE, Google Vertex AI / Gemini API integration, BigQuery FinOps telemetry, and 24/7 Cloud Monitoring HTTPS probes.

### 2. Studio-12 Live Ensemble DSP Workstation & Publishing Pipeline
Deterministic 64-bit Python and browser WebAudio multi-track mixing, mastering (`-14.0 LUFS` `ITU-R BS.1770-4`), and Concert Vault / digital media kit publishing pipeline for live acoustic ensembles (17/17 automated pytest tests passing), scaling from portable 12-track Tascam Model 12 Broadcast Wave (`24-bit/48 kHz BWF`) stage captures to variable multi-input ensembles.

### 3. [Angband 3D](https://angband3d.com) Public Proving Ground (`v11.1.1`, GPL-2.0)
Four classic C/C++ roguelike engines bridged to WebAssembly and a 60fps Three.js/WebGL2 browser, desktop .NET 8 C#, and Android client (45/45 automated test suites passing), strictly isolated from our proprietary repositories.