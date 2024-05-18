## ComfyUI Quickstart

[Pixart support added to ComfyUI by city96](https://github.com/city96/ComfyUI_ExtraModels)

> [!IMPORTANT]
> Download pretrained checkpoints to output/pretrained_models before running ComfyUI!

> [!TIP]
> * See assets/workflows for simple workflow examples.
> * Testing additional ComfyUI extensions: modify the ENTRYPOINT of Dockerfile.comfyui to drop into a shell

Build the container with docker/podman
```bash
docker build -f Dockerfile.comfyui . -t pixart:comfyui
```

Run the container
```bash
docker run --gpus all \
  -p 8188:8188 \
  -v output/pretrained_models:/workspace/ComfyUI/models/checkpoints \
  -v output/pretrained_models/pixart_sigma_sdxlvae_T5_diffusers/text_encoder:/workspace/ComfyUI/models/t5 \
  -v output/pretrained_models/pixart_sigma_sdxlvae_T5_diffusers/vae:/workspace/ComfyUI/models/vae \
  -v output:/workspace/ComfyUI/output \
  -it pixart:comfyui
```

Use a workflow or develop your own!

Sigma CPU T5 encoding for PixArt-Sigma-XL-2-512-MS.pth
<img src="asset/comfyui/Sigma-CPU-T5-512.png" width="512">

Sigma CPU T5 encoding for PixArt-Sigma-XL-2-1024-MS.pth
<img src="asset/comfyui/Sigma-CPU-T5-1024.png" width="512">

Sigma GPU T5 encoding for PixArt-Sigma-XL-2-1024-MS.pth
<img src="asset/comfyui/Sigma-GPU-T5-1024.png" width="512">

Sigma GPU T5 encoding for PixArt-Sigma-XL-2-2K-MS.pth
<img src="asset/comfyui/Sigma-GPU-T5-2048.png" width="512">

