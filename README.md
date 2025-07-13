# wsl-vllm

Run your local vLLM on Windows 11

## Step-by-Step Guide

1. Setup Ubuntu on your Windows Machine: [01_ubuntu.md](01_ubuntu.md)
2. Install/update CUDA Tookit: [02_cuda.md](02_cuda.md)
3. Install UV package manager: [03_python_uv.md](03_python_uv.md)
4. Install and run vLLM: [04_vllm.md](04_vllm.md)

## On Your Next Login

```shell
source .venv/bin/activate
vllm serve ${model-path-name} --gpu_memory_utilization 0.95
```

Example:

```shell
source .venv/bin/activate
vllm serve Qwen/Qwen2.5-VL-3B-Instruct --gpu_memory_utilization 0.95
```

## Download Model and Local Loading

```shell
uv pip install -U "huggingface_hub[cli]"
```

1. Example: Download and run vision LLM
   ```shell
   huggingface-cli download Qwen/Qwen2.5-VL-3B-Instruct --local-dir ./llm/Qwen/Qwen2.5-VL-3B-Instruct
   vllm serve ./llm/Qwen/Qwen2.5-VL-3B-Instruct --gpu_memory_utilization 0.95
   ```
1. Example: Download and run Llama LLM
   ```shell
   huggingface-cli download meta-llama/Llama-3.2-3B-Instruct --local-dir ./llm/meta-llama/Llama-3.2-3B-Instruct
   vllm serve ./llm/meta-llama/Llama-3.2-3B-Instruct --gpu_memory_utilization 0.7 --max_model_len 4096
   ```
