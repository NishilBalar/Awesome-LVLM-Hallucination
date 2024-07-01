# Awesome-LVLM-Hallucination [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

Even though the world has seen the imersive capabilities of large vision language models, particularly in zero-shot inference, such models struggle with hallucinations, which can be referred to as **the generation of text with information that is not present in the visual input**. Lots of research work is going on to tackle this problem, such as hallucinated objects, inaccurate attributes and relationships, unfaithful descriptions, and so on. Possible reasons behind this could be language prior, insufficient visual context, biases and misinformation in the training dataset, and so on.

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
7. **MMHAL-BENCH**: [Aligning Large Multimodal Models with Factually Augmented RLHF](https://arxiv.org/pdf/2309.14525.pdf) (25 September, 2023) [![Star](https://img.shields.io/github/stars/llava-rlhf/LLaVA-RLHF.svg?style=social&label=Star)](https://github.com/llava-rlhf/LLaVA-RLHF) 
     - Introduced novel algorithm called Factually Augmented RLHF (Fact-RLHF) to alleviate the reward hacking phenomenon in RLHF
     - Developed evaluation benchmark MMHAL-BENCH with a special focus on penalizing hallucinations
     - Trained a LLM with RLHF (Llava-RLHF) which shows improved multimodal alignment
8. **LRV (GAVIE)**: [Mitigating Hallucination in Large Multi-Modal Models via Robust Instruction Tuning](https://arxiv.org/pdf/2306.14565.pdf) (29 September, 2023) [![Star](https://img.shields.io/github/stars/FuxiaoLiu/LRV-Instruction.svg?style=social&label=Star)](https://github.com/FuxiaoLiu/LRV-Instruction)
     - LRV-Instruction - positive and negative robust instruction tuning dataset with 400k visual instructions (16 tasks)
     - Negative instruction semantics: (a) Nonexistent Object Manipulation (b) Existent Object Manipulation (c) Knowledge Manipulation
     - GPT4-Assisted Visual Instruction Evaluation (GAVIE)
9. **NOPE**: [Negative Object Presence Evaluation (NOPE) to Measure Object Hallucination in Vision-Language Models](https://arxiv.org/pdf/2310.05338.pdf) (09 October, 2023) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - VQA diagnostic benchmark to measure object hallucination with use of 'Negative Pompt' based questions
     - LLM based generation of 29.5k synthetic negative pronoum (none, no one, nobody. nowhere, neither) dataset
     - Finding: tendency of VLMs to hallucinate more on data with higher lexical diversity, more scene relavent objects (co-occurance) and large answer copes.
10. **HallusionBench**: [An Advanced Diagnostic Suite for Entangled Language Hallucination and Visual Illusion in Large Vision-Language Models](https://arxiv.org/pdf/2310.14566.pdf) (CVPR 2024) [![Star](https://img.shields.io/github/stars/tianyi-lab/HallusionBench.svg?style=social&label=Star)](https://github.com/tianyi-lab/HallusionBench)
     - Language Hallucination + Visual Illusion: 1129 VQA paired with total 346 images
     - It includes topics such as food, math, geometry, statistics, geography, sports, cartoon, famous illusions, movie, meme, etc. and formats such as including logo, poster, figure, charts, table, map, consecutive images, etc.
11. **FAITHSCORE**: [Evaluating Hallucinations in Large Vision-Language Models](https://arxiv.org/pdf/2311.01477.pdf) (02 November, 2023) [![Star](https://img.shields.io/github/stars/bcdnlp/FAITHSCORE.svg?style=social&label=Star)](https://github.com/bcdnlp/FAITHSCORE)
     - Reference-free and fine-grained evaluation metric
     - 1) Recognizer : LLM is used for descriptive content identification of LVLM's prediction
     - 2) Decomposer : LLM is used to generate atomic facts based on recognizer's output
     - 3) Verifier   : Visual Entailment Model (e.g. OFA) is used to verify atomic facts with input image
12. **Bingo**: [Holistic Analysis of Hallucination in GPT-4V(ision): Bias and Interference Challenges](https://arxiv.org/pdf/2311.03287.pdf) (07 November, 2023)  [![Star](https://img.shields.io/github/stars/gzcch/Bingo.svg?style=social&label=Star)](https://github.com/gzcch/Bingo)
     - Total 308 Images and 370 QA Pairs
     - Bias category: Region, OCR and Factual
     - Interferance catogary: Image-to-Image and Text-to-Image
13. **AMBER**: [An LLM-free Multi-dimensional Benchmark for MLLMs Hallucination Evaluation](https://arxiv.org/pdf/2311.07397.pdf) (13 November, 2023) [![Star](https://img.shields.io/github/stars/junyangwang0410/AMBER.svg?style=social&label=Star)](https://github.com/junyangwang0410/AMBER)
     - LLM free evaluation of hallucination using AMBER benchmark
     - Evaluation of hallucination for generative and discriminative task using AMBERSCORE metric (covers existence, attributes and relation types of hallucination)
     - Includes hallucinatory target objects (more likely to be imagined by LVLMs)
14. **RAH-Bench**: [Mitigating Hallucination in Visual Language Models with Visual Supervision](https://arxiv.org/pdf/2311.16479.pdf) (27 Novemebr, 2023) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Introduce fine-grained vision instruction dataset named RAI-30K (built upon panoptic scene graph dataset (PSG))
     - RAH-BENCH vision hallucination evaluation benchmark (3 types: Categorial, Relation and Attribute Hallucination)
     - False Positive Rates as evaluation metric
15. **Behind the Magic, MERLIM**: [Multi-modal Evaluation Benchmark for Large Image-Language Models](https://arxiv.org/pdf/2312.02219.pdf) (03 Decemeber, 2023) [![Star](https://img.shields.io/github/stars/ojedaf/MERLIM.svg?style=social&label=Star)](https://github.com/ojedaf/MERLIM)
     - Proposed a novel test-bed to evaluate IT-LVLMs (Instruction Tuning Large Vision and Language models) on core computer vision tasks
     - Observed poor performance of IT-LVLMs with multiple failure cases in visual grounding
     - Identify problems with IT-LVLMSs like generation of hallucinatory events and sensitivity to the input query 
16. **CCEval**: [HallE-Switch: Controlling Object Hallucination in Large Vision Language Models](https://arxiv.org/pdf/2310.01779.pdf) (03 Decemebr, 2023) [![Star](https://img.shields.io/github/stars/bronyayang/HallE_Switch.svg?style=social&label=Star)](https://github.com/bronyayang/HallE_Switch)
     - Suggest an approach to control object existence hallucination in detailed captions of LVLM
     - Introduced CCEval which is a GPT-4 assisted evaluation method for detailed captioning (Metrics: CHAIR(i&s), Coverage, Average Length, Average Objects)
     - Detailed investigation on LVLM's component that might imfluence hallucination such as alignment of language decoder, volume of instruction data, resolution of input image and so on
     - Introduced a controlling parameters over LLMs (HallE-Control) to condition the inference of objects 
17. **FGHE**: [Mitigating Fine-Grained Hallucination by Fine-Tuning Large Vision-Language Models with Caption Rewrites](https://arxiv.org/pdf/2312.01701.pdf) (04 December, 2023) [![Star](https://img.shields.io/github/stars/Anonymousanoy/FOHE.svg?style=social&label=Star)](https://github.com/Anonymousanoy/FOHE)
     - Dealing with fine-grained object hallucination with ReCaption framework 
     - Two stage frame work : 1) Caption generation with help of ChatGPT 2) Finetuning LVLMs on generated captions
     - Inroduced Fine-Grained Object Hallucination Evaluation (FGHE) which similar to POPE. (manually annotted 50 images with 200 binary questions with type multi-object, attributes and behaviour)
18. **OpenCHAIR**: [Mitigating Open-Vocabulary Caption Hallucinations](https://arxiv.org/pdf/2312.03631.pdf)  (06 Decemeber, 2023) [![Star](https://img.shields.io/github/stars/assafbk/mocha_code.svg?style=social&label=Star)](https://github.com/assafbk/mocha_code)
     - soon
19. **CorrelationQA**: [The Instinctive Bias: Spurious Images lead to Hallucination in MLLMs](https://arxiv.org/pdf/2402.03757.pdf) (06 February, 2024) [![Star](https://img.shields.io/github/stars/MasaiahHan/CorrelationQA.svg?style=social&label=Star)](https://github.com/MasaiahHan/CorrelationQA)
     - soon
20. **ViGoR**: [Improving Visual Grounding of Large Vision Language Models with Fine-Grained Reward Modeling](https://arxiv.org/pdf/2402.06118.pdf) (09 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
21. **VQAv2-IDK**: [Visually Dehallucinative Instruction Generation: Know What You Don’t Know](https://arxiv.org/pdf/2402.09717.pdf) (15 February, 2024) [![Star](https://img.shields.io/github/stars/ncsoft/idk.svg?style=social&label=Star)](https://github.com/ncsoft/idk)
     - soon
22. **MHaluBench**: [Unified Hallucination Detection for Multimodal Large Language Models](https://arxiv.org/pdf/2402.03190.pdf) (20 February, 2024) [![Star](https://img.shields.io/github/stars/OpenKG-ORG/EasyDetect.svg?style=social&label=Star)](https://github.com/OpenKG-ORG/EasyDetect)
     - soon
23. **MAD-Bench**: [How Easy is It to Fool Your Multimodal LLMs? An Empirical Analysis on Deceptive Prompts](https://arxiv.org/pdf/2402.13220.pdf) (20 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
24. **VHTest**: [Visual Hallucinations of Multi-modal Large Language Models](https://arxiv.org/pdf/2402.14683v1.pdf) (22 February, 2024) [![Star](https://img.shields.io/github/stars/wenhuang2000/VHTest.svg?style=social&label=Star)](https://github.com/wenhuang2000/VHTest)
     - soon
25. **Hal-Eval**: [A Universal and Fine-grained Hallucination Evaluation Framework for Large Vision Language Models](https://arxiv.org/pdf/2402.15721.pdf) (24 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
26. [Evaluating and Mitigating Number Hallucinations in Large Vision-Language Models: A Consistency Perspective](https://arxiv.org/pdf/2403.01373.pdf) (03 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
27. ** EvalDial**: [Mitigating Dialogue Hallucination for Large Multi-modal Models via Adversarial Instruction Tuning](https://arxiv.org/pdf/2403.10492.pdf) (15 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
28. **IVL-Hallu**: [PhD: A Prompted Visual Hallucination Evaluation Dataset](https://arxiv.org/pdf/2403.11116.pdf) (17 March, 2024) [![Star](https://img.shields.io/github/stars/jiazhen-code/IntrinsicHallu.svg?style=social&label=Star)](https://github.com/jiazhen-code/IntrinsicHallu)
     - soon
29. **ALOHa**: [A New Measure for Hallucination in Captioning Models](https://arxiv.org/pdf/2404.02904v1.pdf) (3 April, 2024)  ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon 
30. **VALOR-EVAL**: [Holistic Coverage and Faithfulness Evaluation of Large Vision-Language Models](https://arxiv.org/pdf/2404.13874) (22 April, 2024) [![Star](https://img.shields.io/github/stars/haoyiq114/VALOR.svg?style=social&label=Star)](https://github.com/haoyiq114/VALOR)
     - soon 
31. **THRONE**: [An Object-based Hallucination Benchmark for the Free-form Generations of Large Vision-Language Models](https://arxiv.org/pdf/2405.05256) (08 May, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
32. **MRHal-Bench**: [Automated Multi-level Preference for MLLMs](https://arxiv.org/pdf/2405.11165) (18 May, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
33. **VLind-Bench**: [Measuring Language Priors in Large Vision-Language Models](https://arxiv.org/pdf/2406.08702) (13 June, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
34. **MMRel**: [A Relation Understanding Dataset and Benchmark in the MLLM Era](https://arxiv.org/pdf/2406.09121) (13 June, 2024) [![Star](https://img.shields.io/github/stars/niejiahao1998/MMRel.svg?style=social&label=Star)](https://github.com/niejiahao1998/MMRel)
     - soon
35. **Med-HallMark**: [Detecting and Evaluating Medical Hallucinations in Large Vision Language Models](https://arxiv.org/pdf/2406.10185) (14 June, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Medical field hallucination benchmark
     - MediHall Score - evaluation metric
36. **AUTOHALLUSION**: [Automatic Generation of Hallucination Benchmarks for Vision-Language Models](https://arxiv.org/pdf/2406.10900) (16 June, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
37. **CHAIR-MEN**: [Does Object Grounding Really Reduce Hallucination of Large Vision-Language Models?](https://arxiv.org/pdf/2406.14492) (20 June, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
38. **R-BENCH**: [Evaluating and Analyzing Relationship Hallucinations in Large Vision-Language Models](https://arxiv.org/pdf/2406.16449) (24 June, 2024) (ICML2024) [![Star](https://img.shields.io/github/stars/mrwu-mac/R-Bench.svg?style=social&label=Star)](https://github.com/mrwu-mac/R-Bench)
     - Introduce an evaluation benchmark to tackle relation type of hallucination 
     - soon
39. **HQH**: [Evaluating the Quality of Hallucination Benchmarks for Large Vision-Language Models](https://arxiv.org/pdf/2406.17115) (24 June, 2024)  [![Star](https://img.shields.io/github/stars/HQHBench/HQHBench.svg?style=social&label=Star)](https://github.com/HQHBench/HQHBench)
     - Propose a framework called Hallucination benchmark Quality Measurement (HQM) to assess the quality of existing hallucination benchmarks
     - soon
40. Up to Date (1st July) and SOTA research work loading...

Note: 'soon' will be replaced with brief description! 

    
## Detection
1. **FPDO - Reward Model**: [Detecting and Preventing Hallucinations in Large Vision Language Models](https://arxiv.org/pdf/2308.06394.pdf) (AAAI 2024) [![Star](https://img.shields.io/github/stars/hendryx-scale/mhal-detect.svg?style=social&label=Star)](https://github.com/hendryx-scale/mhal-detect)
     - M-HalDetect - Hallucination detection dataset with fine-grained annotations [accurate, inaccurate and analysis]
     - Fine-grained Direct Preference Optimization (FDPO) technique and reward model trained on introduced dataset
     - High correlation of reward model score with human evaluation
2. **HaELM**: [Evaluation and Analysis of Hallucination in Large Vision-Language Models](https://arxiv.org/pdf/2308.15126.pdf) (29 August, 2023) [![Star](https://img.shields.io/github/stars/junyangwang0410/HaELM.svg?style=social&label=Star)](https://github.com/junyangwang0410/HaELM)
     - Discussed LVLMs tendency to response as 'Yes' to judgement type queries
     - Use of ChatGPT to collect hallucination data via iterative prompt modification
     - Open-source LLM trained over this dataset for evaluation of LVLM's response
     - Evaluation results on various LVLMs, Generation length and Top-K of sampling
3. **HallE-Switch**: [Controlling Object Hallucination in Large Vision Language Models](https://arxiv.org/abs/2310.01779) (3 October, 2023) [![Star](https://img.shields.io/github/stars/bronyayang/HallE_Switch.svg?style=social&label=Star)](https://github.com/bronyayang/HallE_Switch)
     - Suggest an approach to control object existence hallucination in detailed captions of LVLM
     - Introduced CCEval which is a GPT-4 assisted evaluation method for detailed captioning (Metrics: CHAIR(i&s), Coverage, Average Length, Average Objects)
     - Detailed investigation on LVLM's component that might imfluence hallucination such as alignment of language decoder, volume of instruction data, resolution of input image and so on
     - Introduced a controlling parameters over LLMs (HallE-Control) to condition the inference of objects 
4. **HalluciDoctor**: [Mitigating Hallucinatory Toxicity in Visual Instruction Data](https://arxiv.org/pdf/2311.13614.pdf) (22 November, 2023)  [![Star](https://img.shields.io/github/stars/Yuqifan1117/HalluciDoctor.svg?style=social&label=Star)](https://github.com/Yuqifan1117/HalluciDoctor)
     - Investigates hallucination toxicity in already existing visual instruction dataset
     - Proposed HalluciDoctor method for automatic elimination of such toxicity
     - Generation of more counterfactual instruction data  with help of HalluciDoctor to improve LVLMs' resistance to hallucination
5. **LogicCheckGPT**: [Logical Closed Loop: Uncovering Object Hallucinations in Large Vision-Language Models](https://arxiv.org/pdf/2402.11622.pdf) (18 february, 2024)  [![Star](https://img.shields.io/github/stars/Hyperwjf/LogicCheckGPT.svg?style=social&label=Star)](https://github.com/Hyperwjf/LogicCheckGPT)
     - Postprocessing output description of LVLMs
     - 5 steps logical loop procedure such as
          - Object extraction, Object-to-Attribute inquiring, Attribute-to-Object inquiring, Logic closed llop check and Hallucination detection and mitigation 
     - Experimental analysis on POPE and MME benchmark     
6. **UNIHD**: [Unified Hallucination Detection for Multimodal Large Language Models](https://arxiv.org/pdf/2402.03190.pdf) (20 February, 2024) [![Star](https://img.shields.io/github/stars/OpenKG-ORG/EasyDetect.svg?style=social&label=Star)](https://github.com/OpenKG-ORG/EasyDetect)
     - Introduce a meta evaluation benchmark called MHALUBENCH
     - Introduce a framework named UNIHD which detect modality-conflicting hallucinations at various levels such as object, attribute, and scene-text, as well as fact-conflicting hallucinations
7. [Detecting and Mitigating Hallucination in Large Vision Language Models via Fine-Grained AI Feedback](https://arxiv.org/pdf/2404.14233) (22 April, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Use of GPT-4/GPT-4v to generate fine-grained feedback for hallucination detection and detection (by supervised finetuning (SFT) of LVLM)
     - Propose automatic pipeline for preference dataset construction
     - Hallucination Severity Aware Direct Prefential Optimization (HSA-DPO) is introduced for mitigation of LVLM's hallucination
8. **MetaToken**: [Detecting Hallucination in Image Descriptions by Meta Classification](https://arxiv.org/pdf/2405.19186) (29 May, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Really cool approach
     - Lightweight method for hallucination detection
9. **Image Textualization**: [An Automatic Framework for Creating Accurate and Detailed Image Descriptions](https://arxiv.org/pdf/2406.07502) (11 June, 2024) [![Star](https://img.shields.io/github/stars/sterzhang/image-textualization.svg?style=social&label=Star)](https://github.com/sterzhang/image-textualization/)
     - soon
10. **MediHallDetector**: [Detecting and Evaluating Medical Hallucinations in Large Vision Language Models](https://arxiv.org/pdf/2406.10185) (14 June, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Medical field hallucination detection
     - soon
11. Up to Date (1st July) and SOTA research work loading...

Note: 'soon' will be replaced with brief description! 

## Mitigation
1. **ObjMLM**: [Plausible May Not Be Faithful: Probing Object Hallucination in Vision-Language Pre-training](https://arxiv.org/pdf/2210.07688.pdf) (10 February 2023) [![Star](https://img.shields.io/github/stars/wenliangdai/VLP-Object-Hallucination.svg?style=social&label=Star)](https://github.com/wenliangdai/VLP-Object-Hallucination)
     - Deals with object hallucination problem of VLMs
     - Discuss the influence of various Vision Language Pretraining (VLP) objective (ITM, ITC and ICLM) and Image encoding methods (region-based, grid-based, and patch-based) on object hallucination
     - Introduce novel VLP objective ObjMLM to mitigate object hallucination
2. **MMCoT**: [Multimodal Chain-of-Thought Reasoning in Language Models](https://arxiv.org/pdf/2302.00923.pdf) (17 February 2023) [![Star](https://img.shields.io/github/stars/amazon-science/mm-cot.svg?style=social&label=Star)](https://github.com/amazon-science/mm-cot)
     - Two stage framework by finetuning language models to perform Multimodal chain-of-thoughts (CoT) which incorporates language (text) and vision (images) modalities
     - Claims state-of-the-art performance of model under 1 billion parameters on ScienceQA benchmark
     - Multimodal-CoT has the merits of mitigating hallucination and enhancing convergence speed
3. **LRV-GAVIE**: [Mitigating Hallucination in Large Multi-Modal Models via Robust Instruction Tuning](https://arxiv.org/pdf/2306.14565.pdf) (26 June, 2023)  [![Star](https://img.shields.io/github/stars/FuxiaoLiu/LRV-Instruction.svg?style=social&label=Star)](https://github.com/FuxiaoLiu/LRV-Instruction)
     - LRV-Instruction - positive and negative robust instruction tuning dataset with 400k visual instructions (16 tasks)
     - Negative instruction semantics: (a) Nonexistent Object Manipulation (b) Existent Object Manipulation (c) Knowledge Manipulation
     - GPT4-Assisted Visual Instruction Evaluation (GAVIE)
4. **LLaVA-RLHF**: [Aligning Large Multimodal Models with Factually Augmented RLHF](https://arxiv.org/pdf/2309.14525.pdf) (25 September, 2023) [![Star](https://img.shields.io/github/stars/llava-rlhf/LLaVA-RLHF.svg?style=social&label=Star)](https://github.com/llava-rlhf/LLaVA-RLHF)
     - Introduced novel algorithm called Factually Augmented RLHF (Fact-RLHF) to alleviate the reward hacking phenomenon in RLHF
     - Developed evaluation benchmark MMHAL-BENCH with a special focus on penalizing hallucinations
     - Trained a LLM with RLHF (Llava-RLHF) which shows improved multimodal alignment
5. **LURE**: [Analyzing and Mitigating Object Hallucination in Large Vision-Language Models](https://arxiv.org/pdf/2310.00754.pdf) (01 October, 2023) [![Star](https://img.shields.io/github/stars/YiyangZhou/LURE.svg?style=social&label=Star)](https://github.com/YiyangZhou/LURE)
     - Introduced LURE framework which is lightweight and compatible post-hoc approach for rectifying object hallucination in LVLMs
     - Statstical analysis of Co-occurence of objects, object uncertainity and object position in generated description which might correlate with object hallucination
     - Uncertain objects are put as placeholder with <IDK> tokens while training LURE and while infernece (for revision)
     - Really popular method
6. **HallE-Switch**: [Controlling Object Hallucination in Large Vision Language Models](https://arxiv.org/pdf/2310.01779.pdf) (3 October, 2023) [![Star](https://img.shields.io/github/stars/bronyayang/HallE_Switch.svg?style=social&label=Star)](https://github.com/bronyayang/HallE_Switch)
     - Suggest an approach to control object existence hallucination in detailed captions of LVLM
     - Introduced CCEval which is a GPT-4 assisted evaluation method for detailed captioning (Metrics: CHAIR(i&s), Coverage, Average Length, Average Objects)
     - Detailed investigation on LVLM's component that might imfluence hallucination such as alignment of language decoder, volume of instruction data, resolution of input image and so on
     - Introduced a controlling parameters over LLMs (HallE-Control) to condition the inference of objects 
7. **Woodpecker**: [Hallucination Correction for Multimodal Large Language Models](https://arxiv.org/abs/2310.16045) (24 October, 2023) [![Star](https://img.shields.io/github/stars/BradyFU/Woodpecker.svg?style=social&label=Star)](https://github.com/BradyFU/Woodpecker)
     - Really popular method
     - Training free, post-hoc method to mitigate hallucination (but computationally expensive!!)
     - 5 steps framework:
        1) Key concept extraction from LVLM's output
        2) Formulation of questions based on key concepts
        3) Visual Knowledge validation (use of open-source object detector + pretrained VQA model)
        4) Visual claim generation (use of fix sentence templates + QA to claim model)
        5) Hallucination Correction (use LLM to correct LVLM's response)
8. **VOLCANO**: [Mitigating Multimodal Hallucination through Self-Feedback Guided Revision](https://arxiv.org/pdf/2311.07362.pdf) (14 November, 2023)  [![Star](https://img.shields.io/github/stars/kaistAI/Volcano.svg?style=social&label=Star)](https://github.com/kaistAI/Volcano)
     - soon
9. **HalluciDoctor**: [Mitigating Hallucinatory Toxicity in Visual Instruction Data](https://arxiv.org/pdf/2311.13614.pdf) (22 November, 2023)  [![Star](https://img.shields.io/github/stars/Yuqifan1117/HalluciDoctor.svg?style=social&label=Star)](https://github.com/Yuqifan1117/HalluciDoctor)
     - Investigates hallucination toxicity in already existing visual instruction dataset
     - Proposed HalluciDoctor method for automatic elimination of such toxicity
     - Generation of more counterfactual instruction data  with help of HalluciDoctor to improve LVLMs' resistance to hallucination
10. **RAH-Bench**: [Mitigating Hallucination in Visual Language Models with Visual Supervision](https://arxiv.org/pdf/2311.16479.pdf) (27 Novemebr, 2023) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
11. **HA-DPO**: [Beyond Hallucinations: Enhancing LVLMs through Hallucination-Aware Direct Preference Optimization](https://arxiv.org/pdf/2311.16839.pdf) (28 November, 2023) [![Star](https://img.shields.io/github/stars/opendatalab/HA-DPO.svg?style=social&label=Star)](https://github.com/opendatalab/HA-DPO)
     - soon
12. **VCD**: [Mitigating Object Hallucinations in Large Vision-Language Models through Visual Contrastive Decoding](https://arxiv.org/pdf/2311.16922.pdf) (28 November, 2023) [![Star](https://img.shields.io/github/stars/DAMO-NLP-SG/VCD.svg?style=social&label=Star)](https://github.com/DAMO-NLP-SG/VCD)
     - Decoding strategy
     - soon
13. **OPERA**: [Alleviating Hallucination in Multi-Modal Large Language Models via Over-Trust Penalty and Retrospection-Allocation](https://arxiv.org/pdf/2311.17911.pdf) (CVPR 2024) [![Star](https://img.shields.io/github/stars/shikiw/OPERA.svg?style=social&label=Star)](https://github.com/shikiw/OPERA)
     - soon
14. **FGHE**: [Mitigating Fine-Grained Hallucination by Fine-Tuning Large Vision-Language Models with Caption Rewrites](https://arxiv.org/pdf/2312.01701.pdf) (04 December, 2023) [![Star](https://img.shields.io/github/stars/Anonymousanoy/FOHE.svg?style=social&label=Star)](https://github.com/Anonymousanoy/FOHE)
     - soon
15. **RLHF-V**: [Towards Trustworthy MLLMs via Behavior Alignment from Fine-grained Correctional Human Feedback](https://arxiv.org/pdf/2312.00849.pdf) (01 December, 2023) [![Star](https://img.shields.io/github/stars/RLHF-V/RLHF-V.svg?style=social&label=Star)](https://github.com/RLHF-V/RLHF-V)
     - fine-grained refined DPO!
     - soon
16. **MOCHa**: [Mitigating Open-Vocabulary Caption Hallucinations](https://arxiv.org/pdf/2312.03631.pdf) (06 December 2023) [![Star](https://img.shields.io/github/stars/assafbk/mocha_code.svg?style=social&label=Star)](https://github.com/assafbk/mocha_code)
     - soon
17. **HACL**: [Hallucination Augmented Contrastive Learning for Multimodal Large Language Model](https://arxiv.org/pdf/2312.06968.pdf) (12 December 2023) [![Star](https://img.shields.io/github/stars/X-PLUG/mPLUG-HalOwl.svg?style=social&label=Star)](https://github.com/X-PLUG/mPLUG-HalOwl)
     - soon
18. **SILKIE**: [Preference Distillation for Large Visual Language Models](https://arxiv.org/pdf/2312.10665.pdf) (17 December, 2023) [![Star](https://img.shields.io/github/stars/vlf-silkie/VLFeedback.svg?style=social&label=Star)](https://github.com/vlf-silkie/VLFeedback)
     - propose VLFeedback dataset for DPO
     - soon
19. **KAM-CoT**: [Knowledge Augmented Multimodal Chain-of-Thoughts Reasoning](https://arxiv.org/pdf/2401.12863.pdf) (23 January, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
20. [Enhancing Multimodal Large Language Models with Vision Detection Models: An Empirical Study](https://arxiv.org/pdf/2401.17981.pdf) (31 January, 2024) [![Star](https://img.shields.io/github/stars/Qirui-jiao/mllm_detection.svg?style=social&label=Star)](https://github.com/Qirui-jiao/mllm_detection)
     - soon
21. **ViGoR**: [Improving Visual Grounding of Large Vision Language Models with Fine-Grained Reward Modeling](https://arxiv.org/pdf/2402.06118.pdf) (09 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
22. **SKIP \N**: [A Simple Method to Reduce Hallucination in Large Vision-Language Models](https://arxiv.org/pdf/2402.01345.pdf) (12 February, 2024) [![Star](https://img.shields.io/github/stars/hanmenghan/Skip-n.svg?style=social&label=Star)](https://github.com/hanmenghan/Skip-n)
     - soon
23. **MARINE**: [Mitigating Object Hallucination in Large Vision-Language Models via Classifier-Free Guidance](https://arxiv.org/pdf/2402.08680.pdf) (13 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
24. **IDK-Instructions**: [Visually Dehallucinative Instruction Generation: Know What You Don’t Know](https://arxiv.org/pdf/2402.09717.pdf) (15 February, 2024)  [![Star](https://img.shields.io/github/stars/ncsoft/idk.svg?style=social&label=Star)](https://github.com/ncsoft/idk)
     - soon
25. **EFUF**: [Efficient Fine-grained Unlearning Framework for Mitigating Hallucinations in Multimodal Large Language Models](https://arxiv.org/pdf/2402.09801.pdf) (15 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
26. **LogicCheckGPT**: [Logical Closed Loop: Uncovering Object Hallucinations in Large Vision-Language Models](https://arxiv.org/pdf/2402.11622.pdf) (18 february, 2024) [![Star](https://img.shields.io/github/stars/Hyperwjf/LogicCheckGPT.svg?style=social&label=Star)](https://github.com/Hyperwjf/LogicCheckGPT)
     - soon
27. **POVID**: [Aligning Modalities in Vision Large Language Models via Preference Fine-tuning](https://arxiv.org/pdf/2402.11411.pdf) (18 february, 2024)  [![Star](https://img.shields.io/github/stars/YiyangZhou/POVID.svg?style=social&label=Star)](https://github.com/YiyangZhou/POVID)
     - soon
28. **Less is More**: [ Mitigating Multimodal Hallucination from an EOS Decision Perspective](https://arxiv.org/pdf/2402.14545.pdf) (22 February, 2024)  [![Star](https://img.shields.io/github/stars/yuezih/less-is-more.svg?style=social&label=Star)](https://github.com/yuezih/less-is-more)
     - decoding strategy
     - soon
29. **CGD**: [Seeing is Believing: Mitigating Hallucination in Large Vision-Language Models via CLIP-Guided Decoding](https://arxiv.org/pdf/2402.15300.pdf) (23 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - decoding strategy
     - soon
30. **IBD**: [Alleviating Hallucinations in Large Vision-Language Models via Image-Biased Decoding](https://arxiv.org/pdf/2402.18476.pdf) (28 February, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - decoding strategy
     - soon
31. **HALC**: [Object Hallucination Reduction via Adaptive Focal-Contrast Decoding](https://arxiv.org/pdf/2403.00425.pdf) (01 March, 2024) [![Star](https://img.shields.io/github/stars/BillChan226/HALC.svg?style=social&label=Star)](https://github.com/BillChan226/HALC)
     - Decodig strategy to tackle object hallucination
     - soon
32. [Evaluating and Mitigating Number Hallucinations in Large Vision-Language Models: A Consistency Perspective](https://arxiv.org/pdf/2403.01373.pdf) (03 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - number hallucination
     - soon
33. **AIT**: [Mitigating Dialogue Hallucination for Large Multi-modal Models via Adversarial Instruction Tuning](https://arxiv.org/pdf/2403.10492.pdf) (15 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
34. **DVP**: [What if...?: Counterfactual Inception to Mitigate Hallucination Effects in Large Multimodal Models](https://arxiv.org/pdf/2403.13513.pdf) (20 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
35. **M3ID**: [Multi-Modal Hallucination Control by Visual Information Grounding](https://arxiv.org/pdf/2403.14003.pdf) (20 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - decoding strategy
     - soon
36. **PENSIEVE**: [Retrospect-then-Compare Mitigates Visual Hallucination](https://arxiv.org/pdf/2403.14401.pdf) (21 March, 2024)  [![Star](https://img.shields.io/github/stars/DingchenYang99/Pensieve.svg?style=social&label=Star)](https://github.com/DingchenYang99/Pensieve)
     - decoding strategy
     - soon
37. **ESREAL**: [Exploiting Semantic Reconstruction to Mitigate Hallucinations in Vision-Language Models](https://arxiv.org/pdf/2403.16167.pdf) (26 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
38. **ICD**: [Mitigating Hallucinations in Large Vision-Language Models with Instruction Contrastive Decoding](https://arxiv.org/pdf/2403.18715.pdf) (27 March, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - decoding strategy
     - soon
39. **FGAIF**: [Aligning Large Vision-Language Models with Fine-grained AI Feedback](https://arxiv.org/pdf/2404.05046.pdf) (07 April, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
40. **Prescribing the Right Remedy**: [Mitigating Hallucinations in Large Vision-Language Models via Targeted Instruction Tuning](https://arxiv.org/pdf/2404.10332.pdf) (16 April, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
41. **FACT**: [Teaching MLLMs with Faithful, Concise and Transferable Rationales](https://arxiv.org/pdf/2404.11129) (17 April, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github) 
     - soon
42. **TVP**: [Exploring the Transferability of Visual Prompting for Multimodal Large Language Models](https://arxiv.org/pdf/2404.11207) (17 April, 2024) [![Star](https://img.shields.io/github/stars/zycheiheihei/Transferable-Visual-Prompting.svg?style=social&label=Star)](https://github.com/zycheiheihei/Transferable-Visual-Prompting)
     - soon
43. **TextSquare**: [Scaling up Text-Centric Visual Instruction Tuning](https://arxiv.org/pdf/2404.12803) (19 April, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
44. **HSA-DPO**: [Detecting and Mitigating Hallucination in Large Vision Language Models via Fine-Grained AI Feedback](https://arxiv.org/pdf/2404.14233) (22 April, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Use of GPT-4/GPT-4v to generate fine-grained feedback for hallucination detection and detection (by supervised finetuning (SFT) of LVLM)
     - Propose automatic pipeline for preference dataset construction
     - Hallucination Severity Aware Direct Prefential Optimization (HSA-DPO) is introduced for mitigation of LVLM's hallucination
45. **Visual Fact Checker**: [Enabling High-Fidelity Detailed Caption Generation](https://arxiv.org/pdf/2404.19752) (30 April - CVPR 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
46. **CSR**: [Calibrated Self-Rewarding Vision Language Models](https://arxiv.org/pdf/2405.14622) (23 May, 2024) [![Star](https://img.shields.io/github/stars/YiyangZhou/CSR.svg?style=social&label=Star)](https://github.com/YiyangZhou/CSR)
     - soon
47. **HIO**: [Alleviating Hallucinations in Large Vision-Language Models through Hallucination-Induced Optimization](https://arxiv.org/pdf/2405.15356) (24 May, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
48. **VDGD**: [Mitigating LVLM Hallucinations in Cognitive Prompts by Bridging the Visual Perception Gap](https://arxiv.org/pdf/2405.15683) (24 May, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
49. **RLAIF-V**: [Aligning MLLMs through Open-Source AI Feedback for Super GPT-4V Trustworthines](https://arxiv.org/pdf/2405.17220) (27 May, 2024) [![Star](https://img.shields.io/github/stars/RLHF-V/RLAIF-V.svg?style=social&label=Star)](https://github.com/RLHF-V/RLAIF-V)
     - soon
50. **AvisC**: [Don’t Miss the Forest for the Trees: Attentional Vision Calibration for Large Vision Language Models](https://arxiv.org/pdf/2405.17820) (28 May, 2024)  [![Star](https://img.shields.io/github/stars/sangminwoo/AvisC.svg?style=social&label=Star)](https://github.com/sangminwoo/AvisC)
     - decoding strategy 
51. **RITUAL**: [Random Image Transformations as a Universal Anti-hallucination Lever in LVLMs](https://arxiv.org/pdf/2405.17821) (28 May, 2024) [![Star](https://img.shields.io/github/stars/sangminwoo/RITUAL.svg?style=social&label=Star)](https://github.com/sangminwoo/RITUAL)
     - soon
52. **HALVA**: [Mitigating Object Hallucination via Data Augmented Contrastive Tuning](https://arxiv.org/pdf/2405.18654) (28 May, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - decoding strategy
     - will publish code soon
53. **NoiseBoost**: [Alleviating Hallucination with Noise Perturbation for Multimodal Large Language Models](https://arxiv.org/pdf/2405.20081) (30 May, 2024) [![Star](https://img.shields.io/github/stars/KaiWU5/NoiseBoost.svg?style=social&label=Star)](https://github.com/KaiWU5/NoiseBoost)
     - soon
54. **mDPO**: [Conditional Preference Optimization for Multimodal Large Language Models](https://arxiv.org/pdf/2406.11839) (17 June, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - soon
55. **DBD**: [Do More Details Always Introduce More Hallucinations in LVLM-based Image Captioning?](https://arxiv.org/pdf/2406.12663) (18 June, 2024) ![Static Badge](https://img.shields.io/badge/not_release-black?logo=github)
     - Introduce novel decoding technique called Differentiated Beam Decoding (DBD)
     - soon
57. **AGLA**: [Mitigating Object Hallucinations in Large Vision-Language Models with Assembly of Global and Local Attention](https://arxiv.org/pdf/2406.12718) (18 June, 2024) [![Star](https://img.shields.io/github/stars/Lackel/AGLA.svg?style=social&label=Star)](https://github.com/Lackel/AGLA)
     - Introduce AGLA, a training-free and plug-and-play decoding framework
     - soon
58. Up to Date (1st July) and SOTA research work loading...
   
Note: 'soon' will be replaced with brief description! 
   
## Survey
1. [DEEP LEARNING APPROACHES ON IMAGE CAPTIONING: A REVIEW](https://arxiv.org/pdf/2201.12944.pdf) (22 August, 2023)
2. [A Survey on Hallucination in Large Vision-Language Models](https://arxiv.org/pdf/2402.00253.pdf) (1 February, 2024)
3. [Visual Hallucination: Definition, Quantification, and Prescriptive Remediations](https://arxiv.org/pdf/2403.17306.pdf) (26 March, 2024)
4. [Hallucination of Multimodal Large Language Models: A Survey](https://arxiv.org/pdf/2404.18930) (29 April, 2024)  [![Star](https://img.shields.io/github/stars/showlab/Awesome-MLLM-Hallucination.svg?style=social&label=Star)](https://github.com/showlab/Awesome-MLLM-Hallucination)
5. [Unveiling Hallucination in Text, Image, Video, and Audio Foundation Models: A Comprehensive Survey](https://arxiv.org/pdf/2405.09589) (20 May, 2024)
6. Up to Date (1st July) and SOTA research work loading...
