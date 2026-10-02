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
    branch: main
    commit: f43d269f476402a4f89b1e3626f6b335b414ea28

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
| `background_removal` | 1.0.0 | `eb843315078e` | `batch_size`, `cache_device`, `cache_dtype`, `cfg`, `clip_device`, `clip_name`, `clip_type`, `denoise`, `encoder_resolution`, `filename_prefix`, `height`, `negative_prompt`, `output_bit_depth`, `output_color_space`, `output_format`, `prompt`, `reference_images`, `sampler_name`, `scheduler`, `seed`, `steps`, `unet_name`, `unet_weight_dtype`, `use_empty_latent`, `vae_name`, `width` |
| `edit` | 1.0.0 | `7cfe57cedde9` | `batch_size`, `cache_device`, `cache_dtype`, `cfg`, `clip_device`, `clip_name`, `clip_type`, `denoise`, `encoder_resolution`, `enhance_prompt`, `filename_prefix`, `height`, `loras`, `negative_prompt`, `output_bit_depth`, `output_color_space`, `output_format`, `pe_clip_device`, `pe_clip_name`, `pe_clip_type`, `pe_max_length`, `pe_min_p`, `pe_mtp`, `pe_presence_penalty`, `pe_repetition_penalty`, `pe_sampling_mode`, `pe_seed`, `pe_system_prompt`, `pe_temperature`, `pe_thinking`, `pe_top_k`, `pe_top_p`, `pe_use_default_template`, `prompt`, `reference_images`, `sampler_name`, `scheduler`, `seed`, `spare_encoder_negative_prompt`, `spare_encoder_prompt`, `spare_encoder_resolution`, `steps`, `unet_name`, `unet_weight_dtype`, `use_empty_latent`, `vae_name`, `width` |
| `t2i` | 1.0.0 | `387d897d7cf0` | `aspect_ratio`, `batch_size`, `cache_device`, `cache_dtype`, `cfg`, `clip_device`, `clip_name`, `clip_type`, `denoise`, `encoder_resolution`, `enhance_prompt`, `filename_prefix`, `loras`, `megapixels`, `negative_prompt`, `output_bit_depth`, `output_color_space`, `output_format`, `pe_clip_device`, `pe_clip_name`, `pe_clip_type`, `pe_max_length`, `pe_min_p`, `pe_mtp`, `pe_presence_penalty`, `pe_repetition_penalty`, `pe_sampling_mode`, `pe_seed`, `pe_system_prompt`, `pe_temperature`, `pe_thinking`, `pe_top_k`, `pe_top_p`, `pe_use_default_template`, `prompt`, `sampler_name`, `scheduler`, `seed`, `size_multiple`, `steps`, `unet_name`, `unet_weight_dtype`, `vae_name` |
