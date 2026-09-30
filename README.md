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

## Related portfolio work

- Employer-facing portfolio: https://aj-kivela-portfolio.lovable.app/
- Public source and application portfolio: https://github.com/ajkivela369-coder/servicebridge-advocate
- SearchSignal SEO + GEO Operations Lab: https://forgesearcher.floot.app/
- Private Forge development repository: available to collaborators/reviewers on request.

## Collaboration

Forge is seeking compute partners, startup programs, technical collaborators, and GPU infrastructure suitable for reproducible AI media, multimodal, and scientific/medical visualization workloads.
