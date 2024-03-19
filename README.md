# Awesome-LVLM-Hallucination [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

Even though the world has seen the imersive capabilities of large vision language models, particularly in zero-shot inference, such models struggle with hallucinations, which can be referred to as the generation of text with information that is not present in the visual input. Lots of research work is going on to tackle this problem, such as hallucinated objects, inaccurate attributes and relationships, unfaithful descriptions, and so on. Possible reasons behind this could be language prior, insufficient visual context, biases and misinformation in the training dataset, and so on.

This repository will provide an organized list of state-of-the-art research papers, relevant code, and a brief description related to hallucinations of the Large-Vision-Language Model (LVLM), also known as the Multimodal Large Language Model (MLLM).

The main intention of this project is to provide a platform where all the research work in the field of hallucination in LVLMs is accessed in a constructive way. If you have any suggestions for intersecting work within this field, kindly contribute them by raising an open issue. I am looking forward to fruitful discussion and learning! 

---
- [Awesome LVLM Hallucination](#Awesome-LVLM-Hallucination)
     - [Hallucination Evaluation Benchmark](#Evaluation-Benchmark)
     - [Hallucination Detection](#Detection)
     - [Hallucination Mitigation](#Mitigation)
     - [Survey](#Survey)
 
---

## Evaluation-Benchmark
1. **CHAIR**: [Object Hallucination in Image Captioning](https://arxiv.org/abs/1809.02156) (EMNLP 2018) [![Star](https://img.shields.io/github/stars/LisaAnne/Hallucination.svg?style=social&label=Star)](https://github.com/LisaAnne/Hallucination)
     - Introduce problem of object hallucination on MSCOCO image captioning task
     -  CHAIR metrics [built upon unique 80 MSCOCO dataset objects]
2. **POPE**: [Evaluating Object Hallucination in Large Vision-Language Models](https://arxiv.org/pdf/2305.10355.pdf) (EMNLP 2023) [![Star](https://img.shields.io/github/stars/AoiDragon/POPE.svg?style=social&label=Star)](https://github.com/AoiDragon/POPE)
     - Object existence hallucination [Yes/No]
     - Random, Popular and Adversial settings on MSCOCO dataset
3. **M-HalDetect**: [Detecting and Preventing Hallucinations in Large Vision Language Models](https://arxiv.org/pdf/2308.06394.pdf) (AAAI 2024)  [![Star](https://img.shields.io/github/stars/hendryx-scale/mhal-detect.svg?style=social&label=Star)](https://github.com/hendryx-scale/mhal-detect)
     - Hallucination detection dataset with fine-grained annotations [accurate, inaccurate and analysis]
     - Fine-grained Direct Preference Optimization (FDPO) technique and reward model dataset
     - High correlation of reward model score with human evaluation
4. coming soon!
       
## Detection
 - will be done soon!

## Mitigation
 - will be done soon!
   
## Survey
 - will be done soon!
