# Forge AI

Forge AI is a local-first AI platform designed to let ordinary consumer laptops orchestrate advanced AI workloads while routing GPU-intensive jobs to the lowest-cost capable compute.

The project is being developed by AJ Kivela, a U.S. Army National Guard veteran who served as a medic and later as a Medical Service Corps officer. Forge grew from a practical constraint: serious AI work should not require a workstation-class GPU or an unlimited cloud budget.

## What Forge includes

- **Forge Core** — shared orchestration, model routing, compute routing, privacy controls, provenance, storage, provider health, and cost policy.
- **GrimForge Cinema** — cinematic production workflows for writing, shot planning, continuity, rendering, QA/rerender, narration, sound, captions, editing, mastering, and production manifests.
- **Elias** — local-first general AI assistant and reasoning environment.
- **Evidence Auditor** — evidence ingestion, provenance, contradiction analysis, organization, and administrative-document workflows.
- **MedForge** — medical/scientific visualization and educational-media tooling.
- **Forge Learn** — companion learning environment that explains the engineering and production workflows used by Forge.
- **Forge Builder** — local-first prompt-to-app workspace with provider-neutral model routing, sandboxed project creation, live local previews, Git snapshots, static/browser QA gates, and explicitly authorized deployment adapters.

## GrimForge production pipeline

```text
Write
  → Cast / reference anchors
  → Shot plan
  → Continuity-locked render
  → QA / rerender
  → Voice + sound
  → Edit + captions
  → Audio mastering
  → Final MP4
  → Production manifest
```

Forge distinguishes **production-quality media** from **draft/previs fallback** and records provider, QA, continuity, and fallback status rather than silently presenting a lower-quality render as production.

## Compute architecture

Forge is designed around a modest laptop acting as the director and orchestrator:

```text
Laptop / Forge UI
  → local planning + continuity
  → privacy / cost policy
  → provider health + routing
  → local renderer OR remote GPU
  → shot QA
  → accepted media returned locally
  → final edit / audio / captions / master
```

The target production GPU tier is **48 GB VRAM for routine media workloads**, with **80 GB-class hardware** reserved for heavier open video-generation workflows when needed.

## Current verification boundary

The current integrated Forge implementation is an **implementation candidate**, not a claim that every media path has passed final production acceptance.

Automated structural, syntax, fixture, UI-regression, Evidence Auditor PDF, Forge Learn synchronization, and assembly checks have passed in the current development line. Real Windows upgrade behavior, real Blender/ComfyUI visual quality, and narrator/voice quality still require target-PC and human visual/audio acceptance.

A successful fixture or CI run therefore does not relabel a previs render as production cinema, a generated medical teaching visual as validated patient-specific anatomy, or an unavailable external engine as connected.

## Why the cloud-GPU work matters

The project is intentionally testing whether advanced AI workflows can remain usable for people who cannot justify or afford a dedicated high-end GPU workstation. Forge is being built around:

- local-first operation where practical;
- explicit privacy classes;
- zero-cost and low-cost routing;
- ephemeral cloud GPU use instead of always-on instances;
- automatic provider fallback and health checks;
- cost per **accepted** shot/output rather than cost per raw attempt;
- reproducible deployment templates for resource-constrained users.

## Current engineering focus

1. Reliable 48–80 GB remote GPU execution for open video models.
2. Image-first cinematic workflows with selective generative motion.
3. Provider health / circuit-breaker routing.
4. Shot-level GPU provisioning and automatic shutdown.
5. Cost/performance benchmarking across providers and GPU classes.
6. Complete long-form GrimForge cinematic episodes rather than isolated clips.
7. Forge Builder: natural-language app planning → editable project → local preview → QA → snapshot → explicitly authorized deployment.
8. Local provider expansion through Ollama / OpenAI-compatible BYOK / desktop model runtimes without treating a ChatGPT subscription as an embedded API credential.

## Current Builder verification

The integrated development line now includes a working Forge Builder backend with:

- local-first intelligence routing;
- explicit privacy / cloud / metered-provider permission gates;
- sandboxed project directories;
- deterministic fallback scaffolds when no model is available;
- local preview URLs;
- per-project Git initialization and named snapshots;
- static HTML/JavaScript QA;
- real browser smoke testing with interaction checks.

The public `forge-builder` repository remains a portable standalone implementation, while the private Forge development repository carries the integrated Forge Core implementation.

## Developer toolchain

See [TOOLCHAIN.md](TOOLCHAIN.md) for the currently verified development and QA tooling used around Forge, including Git/GitHub CLI, Node/npm/pnpm, Python, Ollama, FFmpeg, 12ui, Playwright, agent-browser, Vercel CLI, and Railway CLI.

## Related portfolio work

- Employer-facing portfolio: https://aj-kivela-portfolio.lovable.app/
- Public source and application portfolio: https://github.com/ajkivela369-coder/servicebridge-advocate
- Forge Builder (public standalone implementation): https://github.com/ajkivela369-coder/forge-builder
- SearchSignal SEO + GEO Operations Lab: https://forgesearcher.floot.app/
- Private Forge development repository: available to collaborators/reviewers on request.

## Collaboration

Forge is seeking compute partners, startup programs, technical collaborators, and GPU infrastructure suitable for reproducible AI media, multimodal, and scientific/medical visualization workloads.
