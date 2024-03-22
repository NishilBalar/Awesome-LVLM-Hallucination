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
3. **MME**: [A Comprehensive Evaluation Benchmark for Multimodal Large Language Models](https://arxiv.org/pdf/2306.13394.pdf) (23 June, 2023) [![Star](https://img.shields.io/github/stars/BradyFU/Awesome-Multimodal-Large-Language-Models.svg?style=social&label=Star)](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/tree/Evaluation)
     - MME benchmark covers the evaluation of MLLM's perception and cognition abilities 
     - Perception (Coase-Grained): 4; Perception (Fine-Grained): 5; Perception (OCR): 1; Cognition (Reasoning): 4;  [Total 14 subtasks]
     - Answer in Yes/No format for easy evaluation & 30 advanced MLLMs are benchmarked
4. **M-HalDetect**: [Detecting and Preventing Hallucinations in Large Vision Language Models](https://arxiv.org/pdf/2308.06394.pdf) (AAAI 2024) [![Star](https://img.shields.io/github/stars/hendryx-scale/mhal-detect.svg?style=social&label=Star)](https://github.com/hendryx-scale/mhal-detect)
     - Hallucination detection dataset with fine-grained annotations [accurate, inaccurate and analysis]
     - Fine-grained Direct Preference Optimization (FDPO) technique and reward model dataset
     - High correlation of reward model score with human evaluation
5. **HaELM**: [Evaluation and Analysis of Hallucination in Large Vision-Language Models](https://arxiv.org/pdf/2308.15126.pdf) (29 August, 2023) [![Star](https://img.shields.io/github/stars/junyangwang0410/HaELM.svg?style=social&label=Star)](https://github.com/junyangwang0410/HaELM)
     - Discussed LVLMs tendency to response as 'Yes' to judgement type queries
     - Use of ChatGPT to collect hallucination data via iterative prompt modification
     - Open-source LLM trained over this dataset for evaluation of LVLM's response
     - Evaluation results on various LVLMs, Generation length and Top-K of sampling
6. **CIEM**: [Contrastive Instruction Evaluation Method for Better Instruction Tuning](https://arxiv.org/pdf/2309.02301.pdf) (NeurIPS 2023 Workshop) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Automatic construction of question-answer pair with based on dataset with caption annotation using ChatGPT [Yes/No QA pair] and automatic pipeline for evaluation
     - Constractive instruction tuning (CIT) with Factual and Constractive QA pairs with Chain-of-Thought (CoT) justification
7. **LRV (GAVIE)**: [Mitigating Hallucination in Large Multi-Modal Models via Robust Instruction Tuning](https://arxiv.org/pdf/2306.14565.pdf) (29 September, 2023) [![Star](https://img.shields.io/github/stars/FuxiaoLiu/LRV-Instruction.svg?style=social&label=Star)](https://github.com/FuxiaoLiu/LRV-Instruction)
     - LRV-Instruction - positive and negative robust instruction tuning dataset with 400k visual instructions (16 tasks)
     - Negative instruction semantics: (a) Nonexistent Object Manipulation (b) Existent Object Manipulation (c) Knowledge Manipulation
     - GPT4-Assisted Visual Instruction Evaluation (GAVIE)
8. **NOPE**: [Negative Object Presence Evaluation (NOPE) to Measure Object Hallucination in Vision-Language Models](https://arxiv.org/pdf/2310.05338.pdf) (09 October, 2023) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - VQA diagnostic benchmark to measure object hallucination with use of 'Negative Pompt' based questions
     - LLM based generation of 29.5k synthetic negative pronoum (none, no one, nobody. nowhere, neither) dataset
     - Finding: tendency of VLMs to hallucinate more on data with higher lexical diversity, more scene relavent objects (co-occurance) and large answer copes.
9. **HallusionBench**: [An Advanced Diagnostic Suite for Entangled Language Hallucination and Visual Illusion in Large Vision-Language Models](https://arxiv.org/pdf/2310.14566.pdf) (CVPR 2024) [![Star](https://img.shields.io/github/stars/tianyi-lab/HallusionBench.svg?style=social&label=Star)](https://github.com/tianyi-lab/HallusionBench)
     - Language Hallucination + Visual Illusion: 1129 VQA paired with total 346 images
     - It includes topics such as food, math, geometry, statistics, geography, sports, cartoon, famous illusions, movie, meme, etc. and formats such as including logo, poster, figure, charts, table, map, consecutive images, etc.
10. **FAITHSCORE**: [Evaluating Hallucinations in Large Vision-Language Models](https://arxiv.org/pdf/2311.01477.pdf) (02 November, 2023) [![Star](https://img.shields.io/github/stars/bcdnlp/FAITHSCORE.svg?style=social&label=Star)](https://github.com/bcdnlp/FAITHSCORE)
     - Reference-free and fine-grained evaluation metric
     - 1) Recognizer : LLM is used for descriptive content identification of LVLM's prediction
     - 2) Decomposer : LLM is used to generate atomic facts based on recognizer's output
     - 3) Verifier   : Visual Entailment Model (e.g. OFA) is used to verify atomic facts with input image
11. **Bingo**: [Holistic Analysis of Hallucination in GPT-4V(ision): Bias and Interference Challenges](https://arxiv.org/pdf/2311.03287.pdf) (07 November, 2023)  [![Star](https://img.shields.io/github/stars/gzcch/Bingo.svg?style=social&label=Star)](https://github.com/gzcch/Bingo)
     - Total 308 Images and 370 QA Pairs
     - Bias category: Region, OCR and Factual
     - Interferance catogary: Image-to-Image and Text-to-Image
12. Coming sooon..

ToDO: AMBER, MERLIM, RAH-Bench, HalE-Switch, FGHE, MOCHa, MMVP, MHaluBench, MAD-Bench, Haö-Eval, VHTest, PhD and so on..

    
## Detection
 - will be done soon!

## Mitigation
 - will be done soon!
   
## Survey
 - will be done soon!
