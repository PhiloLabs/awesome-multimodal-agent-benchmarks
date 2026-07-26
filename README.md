# Awesome Multimodal Agent Benchmarks [![Awesome](https://awesome.re/badge.svg)](https://github.com/sindresorhus/awesome)

> A curated list of benchmarks for evaluating multimodal agents — systems that plan, use tools, and act over inputs/outputs beyond plain text.

This list focuses strictly on **benchmarks and evaluation suites**. For agents and models, see the sibling lists:

- [awesome-video-agents](https://github.com/PhiloLabs/awesome-video-agents) — agentic video editing / production systems
- [awesome-any2any-models](https://github.com/PhiloLabs/awesome-any2any-models) — unified any-to-any multimodal models

## Scope & Inclusion Criteria

A benchmark qualifies if it evaluates **agents that operate over multimodal inputs and/or outputs**. It must satisfy **both**:

1. **Agentic** — tasks require multi-step planning, tool use, environment interaction, or long-horizon reasoning. Single-turn QA does not qualify.
2. **Multimodal** — inputs and/or outputs include modalities beyond text: image, video, audio, GUI screenshots, 3D scenes, robot sensors, etc.

**Excluded** (with rationale):

- Pure-text agent benchmarks (AgentBench, SWE-bench, ToolBench) — agentic but not multimodal. Listed under *Related* only.
- Pure multimodal QA benchmarks (MMBench, MME, MMMU, MMVet) — multimodal but not agentic.
- Pure video/image perception benchmarks (Video-MME, EgoSchema, LVBench when used as static QA) — unless cast as an agentic task.

**Included by judgment call**: GUI / web / mobile benchmarks (screenshots are a primary multimodal input), embodied & robotic suites, and visual tool-use benchmarks.

## Contents

- [Comparison Table](#comparison-table)
- [GUI & Computer-Use Agents](#gui--computer-use-agents)
- [Web Agents](#web-agents)
- [Mobile / Android Agents](#mobile--android-agents)
- [Embodied & Robotic Agents](#embodied--robotic-agents)
- [Video Understanding Agents](#video-understanding-agents)
- [Document & Multimodal Reasoning Agents](#document--multimodal-reasoning-agents)
- [General-Purpose Multimodal Agent Suites](#general-purpose-multimodal-agent-suites)
- [Tool-Use & Function-Calling (Multimodal)](#tool-use--function-calling-multimodal)
- [Domain-Specific (Medical, Enterprise, Science)](#domain-specific-medical-enterprise-science)
- [Related Surveys & Aggregators](#related-surveys--aggregators)
- [Related (Text-Only or Non-Agentic) for Context](#related-text-only-or-non-agentic-for-context)
- [Contributing](#contributing)
- [License](#license)

Entries within each section are sorted **newest first** by initial arXiv / publication year.

## Comparison Table

The most-cited / most-used benchmarks at a glance. Sizes are approximate.

| Name | Modalities | Tasks | Size | Year |
| --- | --- | --- | --- | --- |
| OSWorld | Screenshot + A11y tree | Real OS computer-use | 369 tasks | 2024 |
| WindowsAgentArena | Screenshot + A11y tree | Windows OS tasks | 150+ tasks | 2024 |
| WebArena | HTML + Screenshot | Realistic web nav | 812 tasks | 2023 |
| VisualWebArena | Screenshot + HTML | Visually grounded web | 910 tasks | 2024 |
| Mind2Web | HTML + Screenshot | Generalist web nav | ~2k tasks, 137 sites | 2023 |
| Online-Mind2Web | Live web + Screenshot | Live web nav | 300 tasks, 136 sites | 2025 |
| Mind2Web 2 | Live web + Screenshot | Agentic search | 130 tasks | 2025 |
| AndroidWorld | Android screenshots | Mobile app control | 116 tasks, 20 apps | 2024 |
| SPA-Bench | Android screenshots | Smartphone agents | 340 tasks | 2024 |
| GAIA | Text + Image + Files | General assistant | 466 questions | 2023 |
| AssistantBench | Web + Screenshot | Realistic web tasks | 214 tasks | 2024 |
| VisualAgentBench | Mixed (GUI/Embodied/Design) | Visual foundation agent | 5 envs | 2024 |
| EmbodiedBench | RGB + State | Embodied MLLM eval | 1,128 tasks, 4 envs | 2025 |
| VLABench | RGB + Lang | Long-horizon manipulation | 100 task categories | 2024 |
| GTA | Image + Text | Implicit tool use | 229 tasks | 2024 |

## GUI & Computer-Use Agents

- [OSWorld-Human](https://arxiv.org/abs/2506.16042) — Gold human trajectories for every OSWorld task; measures agent step-efficiency. `paper` `code`
- [OSWorld-G / Jedi](https://arxiv.org/abs/2505.13227) — Fine-grained GUI grounding suite (564 samples) paired with the Jedi training set. `paper` `code`
- [ScreenSpot-Pro](https://arxiv.org/abs/2504.07981) — High-res professional GUI grounding across 23 pro apps, 5 domains, 3 OSes. `paper` `code`
- [AgentStudio](https://arxiv.org/abs/2403.17918) — Toolkit + benchmarks (GroundUI, IDMBench) for building general virtual agents. `paper` `code`
- [WindowsAgentArena](https://arxiv.org/abs/2409.08264) — Windows-OS extension of OSWorld with 150+ tasks across Office / browser / system. `paper` `code`
- [OSWorld](https://arxiv.org/abs/2404.07972) — Live Ubuntu / Windows / macOS environment with 369 execution-graded tasks. `paper` `code` `leaderboard`
- [Spider2-V](https://arxiv.org/abs/2407.10956) — 494 enterprise data-engineering tasks across 20 pro apps; GUI + SQL + Python. `paper` `code`
- [CRAB](https://arxiv.org/abs/2407.01511) — Cross-environment (Ubuntu + Android) benchmark with graph-based eval, 120 tasks. `paper` `code`
- [OmniACT](https://arxiv.org/abs/2402.17553) — Desktop + web action grounding dataset for generalist multimodal agents. `paper` `code`
- [ScreenAgent / ScreenSpot](https://arxiv.org/abs/2402.07945) — Original GUI element grounding benchmark (text + icon targets). `paper` `code`

## Web Agents

- [ClawBench](https://arxiv.org/abs/2604.08523) — 283 live-web tasks with execution scoring. `paper` `code`
- [Mind2Web 2](https://arxiv.org/abs/2506.21506) — 130 long-horizon agentic-search tasks evaluated with an Agent-as-a-Judge rubric. `paper` `code`
- [MM-BrowseComp](https://arxiv.org/abs/2508.13186) — Multimodal browsing benchmark; reverse image search and image-grounded retrieval. `paper` `code`
- [Online-Mind2Web](https://arxiv.org/abs/2504.01382) — 300 live-web tasks across 136 sites; reveals overstated progress on static benchmarks. `paper` `code`
- [ST-WebAgentBench](https://arxiv.org/abs/2410.06703) — Safety- and trustworthiness-focused web agent benchmark across 6 risk dims. `paper` `code`
- [WorkArena++](https://arxiv.org/abs/2407.05291) — 682 compositional ServiceNow tasks built atop WorkArena atoms. `paper` `code`
- [AssistantBench](https://arxiv.org/abs/2407.15711) — 214 realistic, time-consuming, multi-site web tasks. `paper` `code`
- [MMInA](https://arxiv.org/abs/2404.09992) — Multi-hop multimodal internet agent benchmark over live websites. `paper` `code`
- [VisualWebArena](https://arxiv.org/abs/2401.13649) — 910 visually grounded tasks across self-hosted Classifieds / Shopping / Reddit. `paper` `code` `leaderboard`
- [WorkArena](https://arxiv.org/abs/2403.07718) — ServiceNow enterprise web tasks; introduced with the BrowserGym environment. `paper` `code`
- [WebArena](https://arxiv.org/abs/2307.13854) — Reproducible self-hosted web environment (shopping / forum / GitLab / CMS), 812 tasks. `paper` `code` `leaderboard`
- [Mind2Web](https://arxiv.org/abs/2306.06070) — First generalist web-agent benchmark; ~2k tasks across 137 real websites. `paper` `code`

## Mobile / Android Agents

- [MobileWorld](https://arxiv.org/abs/2512.19432) — Cross-app, MCP-augmented mobile agent benchmark; ~2x AndroidWorld step count. `paper` `code`
- [A3 (Android Agent Arena)](https://arxiv.org/abs/2501.01149) — Open Android agent arena spanning 21 third-party apps. `paper` `code`
- [SPA-Bench](https://arxiv.org/abs/2410.15164) — Multilingual cross-app smartphone benchmark with interactive scoring + efficiency metrics. `paper` `code`
- [AndroidLab](https://arxiv.org/abs/2410.24024) — XML + SoM Android agent benchmark across 9 apps, 138 tasks. `paper` `code`
- [AndroidWorld](https://arxiv.org/abs/2405.14573) — Dynamic Android benchmark with programmatic reward functions, 116 tasks, 20 real apps. `paper` `code` `leaderboard`
- [B-MoCA](https://arxiv.org/abs/2404.16660) — Benchmarks mobile control agents under randomized device configurations. `paper` `code`

## Embodied & Robotic Agents

- [EmbodiedBench](https://arxiv.org/abs/2502.09560) — 1,128 tasks across EB-ALFRED / EB-Habitat / EB-Navigation / EB-Manipulation for MLLM agents. `paper` `code`
- [VLABench](https://arxiv.org/abs/2412.18194) — 100 categories of long-horizon language-conditioned manipulation; tests VLAs + VLM/LLM workflows. `paper` `code`
- [BEHAVIOR-1K](https://arxiv.org/abs/2403.09227) — 1,000 everyday human activities in OmniGibson with realistic physics. `paper` `code`
- [ALFWorld](https://arxiv.org/abs/2010.03768) — Aligned text + ALFRED embodied environments; canonical sim-to-language transfer. `paper` `code`
- [Habitat 2.0 / 3.0](https://arxiv.org/abs/2310.13724) — Photorealistic interactive simulator for navigation + social rearrangement. `paper` `code`

## Video Understanding Agents

- [LVBench](https://arxiv.org/abs/2406.08035) — Extreme long-video understanding requiring agentic retrieval + reasoning over hours. `paper` `code`
- [VideoAgent benchmarks (NExT-QA / EgoSchema agentic split)](https://arxiv.org/abs/2403.10517) — Long-form video understanding with LLM-as-agent over frames. `paper` `code`
- [Video-MME (agentic subset)](https://arxiv.org/abs/2405.21075) — Used as a probe for tool-using video agents; full set is QA, agentic systems are the standard SOTA. `paper` `leaderboard`

> Note: pure video-QA (EgoSchema, MVBench, Video-MME used statically) is *excluded* per the criteria above; entries here are commonly run with agentic frame-selection / retrieval pipelines.

## Document & Multimodal Reasoning Agents

- [ChartAgent / ChartBench](https://arxiv.org/abs/2510.04514) — Visually grounded tool-augmented agent benchmark over complex charts. `paper` `code`
- [AEC-Bench](https://arxiv.org/abs/2603.29199) — Multimodal benchmark for agentic systems in Architecture / Engineering / Construction. `paper`

## General-Purpose Multimodal Agent Suites

- [TheAgentCompany](https://arxiv.org/abs/2412.14161) — 175 enterprise tasks in a simulated software company; mixes web, GUI, code, comms. `paper` `code` `leaderboard`
- [VisualAgentBench (VAB)](https://arxiv.org/abs/2408.06327) — Unified benchmark across Embodied, GUI, and Visual Design tasks for LMM agents. `paper` `code`
- [BrowserGym Ecosystem](https://arxiv.org/abs/2412.05467) — Unifies MiniWoB++, WebArena, VisualWebArena, WorkArena, AssistantBench, WebLINX under one API. `paper` `code`
- [GAIA](https://arxiv.org/abs/2311.12983) — 466 multi-step general-assistant questions with image / audio / file attachments. `paper` `leaderboard`

## Tool-Use & Function-Calling (Multimodal)

- [M3-Bench](https://arxiv.org/abs/2511.17729) — Multi-modal, multi-hop, multi-threaded tool-using MLLM agent benchmark. `paper`
- [GTA](https://arxiv.org/abs/2407.08713) — 229 real user queries with image attachments; tool + step choices are implicit. `paper` `code` `leaderboard`
- [m&m's](https://arxiv.org/abs/2403.11085) — Tool-use benchmark with 4k+ multi-step plans across 33 tools (vision, audio, text). `paper` `code`

## Domain-Specific (Medical, Enterprise, Science)

- [AgentClinic](https://arxiv.org/abs/2405.07960) — Simulated clinical environments with multimodal images (radiology, pathology) + dialogue. `paper` `code`

## Related Surveys & Aggregators

- [GUI-Agents-Paper-List](https://github.com/OSU-NLP-Group/GUI-Agents-Paper-List) — Continuously updated catalog of GUI-agent papers and benchmarks.
- [Awesome-Agent-Papers](https://github.com/luo-junyu/Awesome-Agent-Papers) — Broad agent survey covering methodology, applications, and benchmarks.
- [HAL Leaderboards](https://hal.cs.princeton.edu/) — Princeton's holistic agent leaderboards (GAIA, SWE-bench, etc.).
- [An Illusion of Progress? Assessing the Current State of Web Agents](https://arxiv.org/abs/2504.01382) — Critical review; introduces Online-Mind2Web.

## Related (Text-Only or Non-Agentic) for Context

These are widely referenced but **fall outside** this list's criteria. Linked for orientation only.

- [AgentBench](https://arxiv.org/abs/2308.03688) — Text-only agent benchmark across 8 environments. Multimodal extensions exist but the core is text.
- [SWE-bench / SWE-bench Multimodal](https://arxiv.org/abs/2310.06770) — Code agents; SWE-bench-M adds screenshot-grounded bugs and is borderline-eligible.
- [ToolBench / API-Bank](https://arxiv.org/abs/2307.16789) — Text tool-use benchmarks.
- [MMBench / MME / MMMU / MMVet](https://arxiv.org/abs/2307.06281) — Multimodal QA, no agent loop.
- [EgoSchema](https://arxiv.org/abs/2308.09126) / [Video-MME](https://arxiv.org/abs/2405.21075) — Long-form video QA; commonly *used by* video agents but the benchmark itself is non-agentic.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). PRs welcome — please verify every link and respect the inclusion criteria.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the maintainers have waived all copyright and related rights to this work.
