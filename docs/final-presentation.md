# Final Presentation

## Reverse Stable Diffusion 2.0

**Course:** CSC 266 — Frontiers in Deep Learning, University of Rochester  
**Team:** Jimmy Yao, Jason Sun, Woody Wu  
**Semester:** Spring 2023

## Task

Reverse the normal text-to-image direction of Stable Diffusion: given a generated image, predict a text prompt similar to the one that produced it.

Evaluation included:

- Kaggle prompt-similarity score based on sentence-transformer cosine similarity.
- Standard captioning metrics such as BLEU, METEOR, ROUGE-L, CIDEr, and SPICE.
- A small seven-image qualitative/evaluation set.

## Dataset

The team filtered DiffusionDB-2M down to approximately 150,000 images by restricting image dimensions and prompt quality and removing highly similar prompts.

## Methods

### Baselines and fine-tuned models

- BLIP
- GIT
- CLIP Interrogator

### SAMGIT

Jimmy's primary project contribution was **SAMGIT**:

1. Use Segment Anything Model (SAM) to detect and crop object regions.
2. Encode the full image and selected object crops.
3. Feed the resulting visual features into GIT for autoregressive text generation.

The hypothesis was that object-level features would provide richer information for reconstructing detailed Stable Diffusion prompts.

### Ensemble methods

The team also evaluated:

- SAM + BLIP
- SAM + BLIP + CLIP Interrogator

## Results

| Method | BLEU-4 | METEOR | ROUGE-L | CIDEr | SPICE | Kaggle | 7-image eval |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| BLIP (pretrained) | 0.243 | 0.253 | 0.478 | 0.848 | 0.199 | 0.401 | 0.373 |
| GIT (pretrained) | 0.411 | 0.302 | 0.602 | 1.329 | 0.236 | 0.371 | 0.353 |
| BLIP (fine-tuned) | 0.050 | 0.121 | 0.285 | 0.172 | 0.087 | 0.346 | 0.298 |
| GIT (fine-tuned) | 0.104 | 0.154 | 0.325 | 0.370 | 0.102 | 0.390 | 0.361 |
| SAMGIT (fine-tuned) | 0.144 | 0.160 | 0.395 | 0.440 | DNF | DNF | **0.456** |
| CLIP Interrogator | — | — | — | — | — | **0.458** | 0.422 |
| SAM + BLIP | — | — | — | — | — | DNF | 0.365 |
| SAM + BLIP + CLIP | — | — | — | — | — | 0.416 | 0.393 |

**DNF:** model could not be evaluated in time or failed during evaluation.

## Takeaways

- SAMGIT produced the strongest score on the team's seven-image evaluation among the fine-tuned approaches.
- The method was too slow to complete full Kaggle evaluation, even with reduced SAM settings.
- The experiments suggested that ranking SAM segments by IoU was not necessarily selecting the most semantically relevant objects.
- The team also observed that fine-tuning could produce substantial distribution drift relative to standard captioning benchmarks.
- CLIP Interrogator produced the strongest completed Kaggle score among the tested methods.

## Original artifact

This Markdown file summarizes the final course presentation delivered in Spring 2023.
