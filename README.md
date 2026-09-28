# SAMGIT — Reverse Stable Diffusion 2.0

Course project for **CSC 266: Frontiers in Deep Learning** at the University of Rochester (Spring 2023).

We explored reconstructing the text prompts used to generate Stable Diffusion images using modern image-captioning and vision-language models.

My primary contribution was **SAMGIT**, which combined Segment Anything with a generative image-to-text model to test whether object-level visual features could improve prompt reconstruction.

## Course artifacts

- [Project proposal (PDF)](docs/proposal.pdf)
- [Final presentation (PDF)](docs/final-presentation.pdf)
- [Project proposal summary](docs/proposal.md)
- [Final presentation summary and results](docs/final-presentation.md)

The final experiments compared pretrained and fine-tuned BLIP/GIT models, SAMGIT, CLIP Interrogator, and several ensemble approaches. SAMGIT achieved the strongest result on our small seven-image evaluation among the fine-tuned models, but was too computationally slow to finish the full Kaggle evaluation.

## Repository

This repository contains the code used for the project experiments.
