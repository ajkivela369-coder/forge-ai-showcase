# Forge AI

Forge AI is a local-first AI platform designed to let ordinary consumer laptops orchestrate advanced AI workloads while routing GPU-intensive jobs to the lowest-cost capable compute.

The project is being developed by AJ Kivela, a disabled U.S. Army National Guard veteran who served as a medic and later as a Medical Service officer. Forge grew directly from a practical constraint: serious AI work should not require a workstation-class GPU or an unlimited cloud budget.

## What Forge includes

- **Forge Core** â€” shared orchestration, model routing, compute routing, privacy controls, provenance, storage, provider health, and cost policy.
- **GrimForge Cinema** â€” complete cinematic production: writing, shot planning, continuity, rendering, QA/rerender, narration, sound, captions, editing, mastering, and production manifests.
- **Elias** â€” local-first general AI assistant and reasoning environment.
- **Evidence Auditor** â€” evidence ingestion, provenance, contradiction analysis, organization, and administrative-document workflows.
- **MedForge** â€” medical/scientific visualization and educational-media tooling.
- **Forge Learn** â€” companion learning environment that explains the actual engineering and production workflows used by Forge.

## GrimForge production pipeline

```text
Write
  â†’ Cast / Reference anchors
  â†’ Shot plan
  â†’ Continuity-locked render
  â†’ QA / rerender
  â†’ Voice + sound
  â†’ Edit + captions
  â†’ Audio mastering
  â†’ Final MP4
  â†’ Production manifest
```

Forge distinguishes **production-quality media** from **draft/previs fallback** and records provider, QA, continuity, and fallback status rather than silently presenting a lower-quality render as production.

## Compute architecture

Forge is designed around a modest laptop acting as the director and orchestrator:

```text
Laptop / Forge UI
  â†’ local planning + continuity
  â†’ privacy / cost policy
  â†’ provider health + routing
  â†’ local renderer OR remote GPU
  â†’ shot QA
  â†’ accepted media returned locally
  â†’ final edit / audio / captions / master
```

The target production GPU tier is **48 GB VRAM for routine media workloads** (for example L40S / RTX-class hardware), with **A100 80 GB or comparable hardware** reserved for heavier open video-generation workflows.

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

1. Reliable 48â€“80 GB remote GPU execution for open video models.
2. Image-first cinematic workflows with selective generative motion.
3. Provider health / circuit-breaker routing.
4. Shot-level GPU provisioning and automatic shutdown.
5. Cost/performance benchmarking across providers and GPU classes.
6. Complete long-form GrimForge cinematic episodes rather than isolated clips.

## Related links

- Portfolio: https://aj-kivela-portfolio.lovable.app/
- Private development repository: available to collaborators/reviewers on request.
- Public project updates and technical materials will be added here as Forge develops.

## Collaboration

Forge is actively seeking compute partners, startup programs, technical collaborators, and GPU infrastructure suitable for reproducible AI media, multimodal, and scientific/medical visualization workloads.

