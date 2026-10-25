# Thunderbear Studios?

**Deterministic verification, multi-file context slicing, and AST-linked project memory for AI coding agents.**

- **Resonant MCP Server & Setup**: [resonantexo.com](https://resonantexo.com) (`https://resonantexo.com/api/mcp`)
- **Engineering & Literature Overview**: [thunderbearstudios.org](https://thunderbearstudios.org)
- **Live Polyglot Proving Ground**: [angband3d.com](https://angband3d.com) ([`ThunderbearStudios/angband3d`](https://github.com/ThunderbearStudios/angband3d) ? GPL-2.0)

---

## Why We Built Resonant MCP

Independent university benchmarks show that even frontier models (Claude Sonnet/Opus, GPT-4o, OpenAI o1/o3-mini) run into three recurring problems on real multi-file codebases:

1. **Fixing one thing breaks another**: Updating a shared function without checking its downstream callers or edge-case behavior silently breaks other files.
2. **Context overload & stale notes**: Dumping full files and long chat histories into the prompt wastes tokens and mixes outdated architectural notes with current code ([LongMemEval, ICLR 2025](https://arxiv.org/abs/2410.10813)).
3. **Silent security & runtime shortcuts**: Nearly half of functionally passing AI backend solutions introduce common security shortcuts ([CWEval, arXiv:2501.08200](https://arxiv.org/abs/2501.08200); [BaxBench, arXiv:2502.11844](https://arxiv.org/abs/2502.11844)).

**Resonant MCP (`resonant-exocortex`)** is a deterministic Python Model Context Protocol server that gives your existing AI assistant (**Claude Code**, **Cursor**, **Windsurf**, or **Antigravity**) fast AST, bytecode, and SQLite verification tools that run in `<3ms` at zero LLM token cost.

---

## Connect the Live MCP Server in 30 Seconds

Run one command in Claude Code:

```bash
claude mcp add --transport http resonant-exocortex https://resonantexo.com/api/mcp
```

Or add to `.mcp.json` / `.cursor/mcp.json` / `mcp_config.json`:

```json
{
  "mcpServers": {
    "resonant-exocortex": {
      "url": "https://resonantexo.com/api/mcp"
    }
  }
}
```

### Core MCP Tools Available Immediately

| Tool | What It Does |
| :--- | :--- |
| **`resonant_verify_cegar`** | Compares `old_code` vs. `code` before saving?running AST contract diffing and sandboxed Python bytecode across boundary inputs (`None`, `0`, `-1`, `""`, `[]`, `{}`) to catch dropped guards, broken signatures, blocked async loops, audio callback allocations, and CWE shortcuts in `<3ms`. |
| **`resonant_architect_orient`** | Extracts only the target function signatures, preconditions, return contracts, and shared-state callers across your files (~85% fewer tokens than raw file dumps). |
| **`resonant_memory_jtms`** | Links project architectural decisions in SQLite to the SHA-256 hash of the normalized AST of the functions they depend on?automatically flagging stale notes (`STALE_AST_DRIFT`) when code changes. |
| **`resonant_evolve_guardrail`** | Diffs a broken AST against its fixed AST to synthesize a reusable structural check in `<1ms`. |
| **`resonant_honesty_audit`** | Verifies technical claims against live symbol indexes and test exit codes (`PROVED`, `HYPOTHESIS`, or `REFUTED`). |

---

## Live Systems

| System | Status | Links |
| :--- | :--- | :--- |
| **Resonant MCP (`resonant-exocortex` v2.4)** | **Live Production** (6/6 JSON-RPC 2.0 MCP tools, free public sandbox + Pilot keys) | [resonantexo.com](https://resonantexo.com) |
| **Angband 3D WebGL & Android (v10.9.0)** | **Live Production** (C/C++ WASM + Three.js 60fps proving ground; 29/29 JS suites, 11/11 browser smoke tests) | [angband3d.com](https://angband3d.com) ? [GitHub Repo](https://github.com/ThunderbearStudios/angband3d) |

---

## Contact & Pilot Evaluation Keys

- **Public Sandbox**: Free immediate access at `https://resonantexo.com/api/mcp` (50 tool calls/day per IP).
- **Pilot & Evaluator Keys (`X-Resonant-Key`)**: For a dedicated `rk_pilot_...` key (5,000 calls/day with isolated persistent SQLite memory) or a technical walkthrough, contact **dev@thunderbearstudios.org** or **founder@thunderbearstudios.org**.
