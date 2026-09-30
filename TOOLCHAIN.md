# Forge Development Toolchain

This file records tools that are currently installed or intentionally supported around the Forge development workflow. It is a capability inventory, not a claim that every external provider is authenticated or used in production.

## Core development

- Git
- GitHub CLI
- Node.js 24
- npm
- pnpm
- Python 3.12
- FastAPI / Uvicorn in the Forge core environment

## Local AI and media

- Ollama for local model serving
- OpenAI-compatible BYOK routing as an optional adapter
- Desktop/local model runtimes may be used when they expose a compatible local endpoint
- FFmpeg for media assembly, inspection, and transcoding
- Blender paths are supported by Forge media workflows where installed and validated

## UI and browser QA

- 12ui Design for non-trivial interface exploration and design conversion
- Playwright
- agent-browser
- Chrome for Testing dedicated to automated browser QA

Forge Builder browser acceptance checks include real page load, content rendering, error-overlay inspection, interactive-element discovery, and interaction verification before deployment is considered.

## Deployment adapters

- Vercel CLI
- Railway CLI

Installing a CLI does not authorize deployment. Forge treats deployment as an explicit action and keeps provider credentials separate from generated applications.

## Architecture rule

A normal ChatGPT subscription is not treated as an API credential embedded in Forge. The model layer is provider-neutral:

```text
Forge request
  -> privacy / cost policy
  -> model router
  -> local model OR explicitly authorized external provider
  -> tool execution / project changes
  -> QA
  -> snapshot
  -> optional explicit deployment
```

This keeps the application usable when one provider is unavailable and makes local-first use the default rather than a fallback.
