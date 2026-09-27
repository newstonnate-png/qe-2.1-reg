# qe-2.1-reg — the published Registry

**Generated. Do not edit anything here by hand.** Every file is written by the publish step in
a private repository and overwritten wholesale on the next publish, so a change made here is
lost and, worse, is a change no Job will ever have been traced to.

## What this is

The **Registry** a Runpod Worker fetches when it starts: it names the Workflows the Endpoint
can run, carries each one's Node graph in ComfyUI's API format, and declares the Parameters each
Workflow exposes. A Job names one Workflow from this file and supplies Parameters; the caller
never sends graph structure.

| File | What it is |
|---|---|
| `registry.json` | The Registry. This is the file a Worker fetches. |
| `schema.json` | The JSON Schema `registry.json` validates against. |

## Where it came from

    repo:   https://github.com/newstonnate-png/qwen-2.1-runpod-serverless
    branch: spec/v1-worker
    commit: 7b0fa919dabe221c368362a8231d7a62bbe2d1b9

That commit is the source of truth. This repository is a **mirror**: it is published from that
commit and never edited in place, so a result a Worker returns can be traced back to something
reviewable.

## Why it is public

A Worker fetches this with **no credential**, deliberately. The Worker is the wrong place for a
secret, and a credential there would add a rotation duty plus a second way for a cold start to
fail (ADR-0007). The accepted cost is that the Node graphs below are world-readable. They carry
sampler settings, steps, cfg and model filenames — no prompts and no images.

## Workflows

| Name | Version | Graph hash | Parameters |
|---|---|---|---|
| `background_removal` | 1.0.0 | `59ed2c72fc63` | `prompt`, `seed`, `steps` |
| `edit` | 1.0.0 | `b4b7196c2cea` | `prompt`, `seed`, `steps` |
| `t2i` | 1.0.0 | `387d897d7cf0` | `aspect_ratio`, `megapixels`, `prompt`, `seed`, `steps` |
