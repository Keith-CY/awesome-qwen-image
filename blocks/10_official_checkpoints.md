<p id="official" align="center">◆◇◆◇◆◇◆◇◆◇◆◇◆◇◆◇◆◇◆◇◆◇◆◇◆</p>

## ▓ Official checkpoints

The reference weights. Start here before touching any community conversion.

<p id="official-base" align="center">· · · · · · · · · · · · · ·</p>

### ▣ Base model

| Name | Precision | Layout | DiT | Text encoder | VAE | Links |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Qwen-Image-2.1** | ![bf16][badge-bf16] | diffusers | 14.23 GB | 17.53 GB (Qwen3-VL-8B) | 1.35 GB | [![][gh-Qwen]](https://huggingface.co/Qwen/Qwen-Image-2.1) |

The reference release, and the only repo you need for a standard Diffusers setup. The DiT and text encoder ship as numbered safetensors shards with an index, so pull the repo rather than a single file.

<p id="official-turbo" align="center">· · · · · · · · · · · · · ·</p>

### ▣ Official Turbo

| Name | Precision | Layout | DiT | Text encoder | VAE | Links |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Qwen-Image-2.1-Turbo** | ![bf16][badge-bf16] | diffusers | 14.23 GB | 17.53 GB (Qwen3-VL-8B) | 0.68 GB | [![][gh-Qwen]](https://huggingface.co/Qwen/Qwen-Image-2.1-Turbo) |

Qwen's own accelerated checkpoint, released **2026-10-09**: the same 7B architecture at **8 denoising steps**, **CFG 1.0** by default, and the recommended sampling schedule is carried *inside the checkpoint*, so `QwenImage21Pipeline` configures the sampler itself — no manual sigma grid. Prefix KV caching reuses the text and reference-image context across steps, which is where the speed comes from on editing. Needs a diffusers build with pipeline-configured sampling sigmas (`transformers>=5.17.0`; support landed in diffusers PR #14950). Card examples run text-to-image at 1696×2528 and editing at 2048×2048. The ComfyUI pre-split build of these weights is the **Turbo** rows in the Comfy-Org table below; the community few-step lines live under [Turbo](#turbo).

<p id="official-comfy" align="center">· · · · · · · · · · · · · ·</p>

### ▣ ComfyUI official

**[Comfy-Org](https://huggingface.co/Comfy-Org/Qwen-Image-2.1)** — the Day-0 ComfyUI repackage, now covering the base model and the official Turbo side by side. Files land directly in `models/` with no renaming.

| Name | Precision | Size | Links |
| :--- | :---: | :---: | :---: |
| **Image Model** | ![bf16][badge-bf16] | 14.23 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/diffusion_models/qwen_image_2.1_bf16.safetensors) |
| **Image Model** | ![int8][badge-int8] | 7.26 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/diffusion_models/qwen_image_2.1_int8_convrot.safetensors) |
| **Image Model (Turbo)** | ![bf16][badge-bf16] | 14.23 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/diffusion_models/qwen_image_2.1_turbo_bf16.safetensors) |
| **Image Model (Turbo)** | ![int8][badge-int8] | 7.26 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/diffusion_models/qwen_image_2.1_turbo_int8_convrot.safetensors) |
| **Text Encoder** | ![bf16][badge-bf16] | 17.53 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/text_encoders/qwen3vl_8b_bf16.safetensors) |
| **Text Encoder** | ![int8][badge-int8] | 9.35 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/text_encoders/qwen3vl_8b_int8_convrot.safetensors) |
| **Text Encoder** | ![w4a8][badge-w4a8] | 6.31 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/text_encoders/qwen3vl_8b_w4a8.safetensors) |
| **Prompt Engine T2I** | ![int8][badge-int8] | 9.47 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/text_encoders/qwen3.5_9b_qwen_image_2.1_pe_t2i.int8_convrot.safetensors) |
| **Prompt Engine I2I** | ![int8][badge-int8] | 9.47 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/text_encoders/qwen3.5_9b_qwen_image_2.1_pe_i2i.int8_convrot.safetensors) |
| **VAE** | ![bf16][badge-bf16] | 0.68 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/vae/qwen_image_2.1_vae_bf16.safetensors) |
| **ControlNet Union** | ![bf16][badge-bf16] | 7.55 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/model_patches/qwen_image_2.1_fun_controlnet_union_bf16.safetensors) |
| **ControlNet Union** | ![int8][badge-int8] | 3.78 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/model_patches/qwen_image_2.1_fun_controlnet_union_int8_convrot.safetensors) |
| **Turbo LoRA** | ![bf16][badge-bf16] | 0.91 GB | [![][gh-Comfy--Org]](https://huggingface.co/Comfy-Org/Qwen-Image-2.1/resolve/main/loras/qwen_image_2.1_turbo_lora_avg_rank_178_bf16.safetensors) |

> [!TIP]
> `ConvRot` files are ComfyUI's native rotated-channel integer format. Use a recent ComfyUI build and load them with the standard diffusion-model and text-encoder loaders — no custom nodes required.
>
> Destination folders: **Image Model** → `models/diffusion_models/`, **Text Encoder** and both **Prompt Engine** rows → `models/text_encoders/`, **VAE** → `models/vae/`, both **ControlNet Union** rows → `models/model_patches/`, **Turbo LoRA** → `models/loras/`.
>
> The two **Image Model (Turbo)** rows are the official 8-step checkpoint pre-split for ComfyUI — same weights as the Qwen repo above, 8 steps and CFG 1. If you would rather keep the base DiT and switch speed at runtime, the **Turbo LoRA** row is the adapter extracted from those weights (average rank 178, by Kijai): load it on the BF16 base with `LoraLoaderModelOnly` at strength 1.0, and do not stack it on a Turbo model.
>
> The two ControlNet rows are the Alibaba PAI Union checkpoint repacked, not an official Qwen release — the int8 build is the cheapest ControlNet here by half. The first **Image Model** row also ships as `model_patches/`, so a ComfyUI ControlNet workflow wants a matching-precision base.

