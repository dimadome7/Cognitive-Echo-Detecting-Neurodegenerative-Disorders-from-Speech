## Overview
Accurate and early detection of neurodegenerative diseases like Amyotrophic Lateral Sclerosis (ALS) is critical, yet current diagnostic methods are often subjective and may miss subtle early
symptoms. Speech provides a non-invasive, information-rich biomarker that reflects both cognitive and motor changes. In this work, we investigate automated classification of ALS and dysarthria
severity from speech using deep learning.

To address this challenge, we propose a novel speech-based classification architecture that leverages pre-trained self-supervised audio models and attention-driven representation learning.
At a high level, our approach extracts informative embeddings from multiple recordings per subject using Wav2Vec, aggregates them into a unified subject-level representation, and performs 
classification using a lightweight MLP classifier. This design aims to enhance sensitivity to subtle acoustic biomarkers while improving robustness across subjects, ultimately enabling more
accurate disease severity classification compared to existing baselines.

## Results
By adopting a Wav2Vec encoder with LoRA fine-tuning and an attention-based pooling mechanism, we substantially improved classification performance. Our best model achieved a Macro-F1 of ***0.824***,
nearly doubling our baseline performance (***0.437***).

Our ablation studies demonstrated that attention pooling and weighted cross-entropy were important contributors to performance, whereas alternatives  like class-balanced focal loss or 
mean-pooling were less effective in our architecture. Weighted sampling further helped stabilize our model’s performance for rare classes. 

Our findings highlight the potential of pretrained speech models for clinical audio analysis, as well as emphasize the importance of addressing data imbalance and subtle class distinctions in 
the detection of neurodegenerative disorders.
