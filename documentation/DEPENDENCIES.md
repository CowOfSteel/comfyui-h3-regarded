# Dependencies and Environment

## Core setup

- **ComfyUI core:** `0.33.0`
- **Frontend:** `1.49.6`
- **GPU:** NVIDIA RTX 3090 Ti, 24 GB VRAM
- **Primary task:** MiniMax H3 `ref2va`
- **Sampler:** `res_multistep`
- **Scheduler:** `simple`
- **Output:** 24 fps, 8-bit, sRGB

## Models used

**Images**
OpenAI's Image 2.0, as of September 1st, 2026.

**Diffusion**
`MiniMaxH3\minimax_h3_ref2va_pruned_int8_convrot.safetensors`

**Text encoders**
- `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`
- `qwen3vl_32b_minimax_h3_w4a8_mixed.safetensors`

**Video VAE**
`minimax_h3_video_vae_int8_convrot.safetensors`

**Audio VAE**
`minimax_h3_audio_vae_fp32.safetensors`

**Turbo LoRA**
`minimax_h3_ref2v_turbo_4step_v0.1_comfyui_bf16.safetensors`

Strength is `1.0` when enabled.

## Additional nodes

The workflows use ComfyUI core H3 nodes plus Video Helper Suite loaders for prior-video and audio references:

- `VHS_LoadVideo`
- `VHS_LoadAudioUpload`

Utility nodes visible in the graphs include `ResolutionSelector`, `ComfySwitchNode`, `ComfyMathExpression`, and standard primitive nodes.

## Reproduction note

Several shot workflows also load earlier generated clips or project reference assets by filename. Those files need to be relinked when reproducing the workflows outside the original project directory.

Where a stock template note conflicts with an actual loader value, the loader value in the submitted JSON is authoritative.
