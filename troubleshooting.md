# Troubleshooting

## vLLM

1. FlashInfer

   ```
   WARNING 07-13 16:24:46 [topk_topp_sampler.py:59] FlashInfer is not available. Falling back to the PyTorch-native implementation of top-p & top-k sampling. For the best performance, please install FlashInfer.
   ```

   Solution:

   ```
   uv pip install flashinfer-python
   ```
