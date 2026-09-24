# Project Proposal

## Exploring the Use of State-of-the-Art Image Captioning for Predicting Text Prompts in Stable Diffusion

**Course:** CSC 266 — Frontiers in Deep Learning, University of Rochester  
**Team:** Jimmy Yao, Woody Wu, Jingxuan Sun  
**Semester:** Spring 2023

## Research question

Can modern image-captioning and vision-language models recover the text prompts used to generate Stable Diffusion images?

The project was motivated by the Stable Diffusion — Image to Prompts Kaggle competition. We proposed comparing several approaches for reconstructing prompts from generated images, including CLIP-based captioning, BLIP, dense image captioning, and ensemble methods.

## Proposed methods

- Build or fine-tune image-to-text models using prompt-image pairs from DiffusionDB and generated Stable Diffusion data.
- Compare CLIP/GPT-2-style captioning, BLIP, and dense image-captioning approaches.
- Use CLIP Interrogator as a baseline.
- Evaluate prompt similarity using the Kaggle competition metric and standard image-captioning metrics.

## Jimmy's planned contribution

Jimmy was responsible for the dense image / image-to-prompt direction. The proposed approach used region-level visual information to generate more detailed prompt reconstructions, motivated by the observation that Stable Diffusion prompts often contain multiple object and style descriptions.

The final implementation of this direction became **SAMGIT**, which combined Segment Anything with GIT.

## Original artifact

This Markdown file summarizes the original course proposal. The original proposal was prepared in Spring 2023.
