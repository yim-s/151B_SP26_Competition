# CSE 151B Competition — Final Code Submission

## Overview
The competition aims to adapt a small pre-trained language model (Qwen3-4B-Thinking-2507) to mathematical reasoning tasks. The goal is to improve the mathematical reasoning performance of the model.

#### Runtime configuration used by the author:
* GPU: one A100 (High-RAM) on Google Colab
* Approximate total inference time: a full inference run over ```private.jsonl``` takes about 1.7 hours on this exact runtime configuration

> The pipeline was developed and tested solely on Google Colab. We do not guarantee adaptability to other runtimes. You may need to adjust settings to adapt different environments or hardware.
<br>

## Get Started
1. Install dependencies.
2. Run the pipeline from the repository root:
   ```python run_inference.py```
3. Collect the output. When inference finishes, the final submission CSV will be available at  ```results/submission.csv```
<br>

## Appendix A: Dependency Installation Requirement

Run the following command in Google Colab, or use the equivalent command for your runtime:
```
pip install sympy numpy "transformers<=4.57" vllm==0.19.1 tqdm bitsandbytes antlr4-python3-runtime==4.11.1 ipykernel jupyter latex2sympy2_extended
```
> If you are using Google Colab, you may need to restart your runtime after installing the dependencies.
<br>

## Appendix B: Contents

| File | Description |
|---|---|
| `run_inference.py` | Main entry point |
| `judger.py` | Response scoring logic |
| `utils.py` | Utilities used by `judger.py` |
| `data/public.jsonl` | Public dataset with ground-truth answers |
| `data/private.jsonl` | Private dataset without ground-truth answers |
| `results/` | Output JSONL and CSV files written at runtime |
