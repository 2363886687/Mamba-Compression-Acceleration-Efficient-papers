# Mamba-Compression-Acceleration-Efficient-papers

## Token reduction

:rocket:R-MeeTo 
https://github.com/NUS-HPC-AI-Lab/R-MeeTo

&emsp;  Token merging + Re-training
  
&emsp;  Inspired by ToMe, in the token merging stage, this paper first divides tokens into odd and even sequence, then calculate their distance, and finally merge the most relevent r pairs. The Retraining stage extremely quickly restore the accuracy of the token merged model.

:rocket:Famba-V （ECCV 2024）
https://github.com/AIoT-MLSys-Lab/Famba-V

&emsp;Also based on ToMe, this paper proposes a suit of cross-layer choice strategies in Vim.

:rocket:Exploring Token Pruning in Vision State Space Models（NeurIPS 2024）

https://github.com/ZLKong/ToP-ViM

&emsp;They recognize the failure of using traditional token pruning in SSMs is the naive token reduction will disrupt the sequence relationship between neighbours. They propose the pruning-aware hidden state alignment method to maintain the hidden states flow and a token importance evaluation metric for pruning.


:rocket:Rethinking Token Reduction for State Space Models

https://github.com/wuyushuwys/ToR_SSM

&emsp; Combining token merging and pruning, they have taken both token similarities and importance score into consideration. They evaluate token importance by aggregating the clipped values in channels of each token. Their algorithm can be concluded as first divide all tokens into two groups based on their importance, and then merge the most similar token pairs.

⭐:LATIM: Measuring Latent Token-to-Token Interactions in Mamba Models

https://github.com/deep-spin/latim

They propose a method for understanding Mamba process on token-level. They calculate "Token-to-Token Importance" from an attention decomposition perspective intrigued by similar works in Transformer. The experiment is conducted in field of language models.

## Token reduction in ViT
🚀 Agglomerative Token Clustering ECCV 2024

They introduce a classical clustering algorithem, Agglomerative Clustering, to conduct clustering in ViT without anymore learning neither fine-tuning. This algorithm starts with every element itself as a cluster, and then these elements are combined iteratively according to some linkage function. There're 3 linkage functions used in the paper. Finally, they use a weighted average in each cluster.

:rocket:Not All Tokens Are Equal: Human-centric Visual Analysis via Token Clustering Transformer CVPR2022

They believe not all tokens should be sent into ViT modules because the semantic information in different tokens is different. So they propose a Clustering-based Token Merge (CTM) Block, which first cluster tokens and then merge tokens in the same cluster into one token. In clustering stage, they combine local density and the distance indicator as scores to identify cluster centers and selecting tokens. In feature merging stage, they introduce an importance score P to assign different weights to tokens in merging operation.

:rocket:PaCa-ViT: Learning Patch-to-Cluster Attention in Vision Transformers CVPR2023

In order to alleviate the quadratic complexity of patch-to-patch attention in ViT, they propose token clustering to substitute the traditional patch-to-patch attention mechanism with patch-to-cluster attention. They use Clustering via Convolution and Clustering via MLP to learn the process of clustering, with every learned cluster owns similar attribute to class tokens. The process is learned end-to-end.


:rocket:NOT ALL PATCHES ARE WHAT YOU NEED:  EXPEDITING VISION TRANSFORMERS VIA  TOKEN REORGANIZATIONS ICLR2022

Previous studies have shown the cls token in ViTs pays more attention to some certain class-specific tokens and neglects some irrelevant tokens to some extent. They utilizes the attentiveness characteristic of cls token to identify attentive tokens and fuse the inattentive tokens. Specifically, they compute the average attentiveness values of multiple heads as the selection creterion and use a weighted average operation to fuse the inattentive tokens.

## Quantization
:rocket: MambaQuant ICLR2025

https://github.com/MambaQuant/MambaQuant

&emsp; They propose an enhanced Hadamard matrices to overcome three kinds of hard layers in Mamba: Gate Projection, Output Projection and Matrix Multiplication, which show extreme unequal outliers across channels. Generally, they convert the unequal variances of activations to the enhanced Hadamard matrices so the activations will be relatively uniformed. Secondly, they improved the SiLU activation into S-SiLU to deal with Projection and Matmul furthermore. In detail, an introduced smoothing parameter s first fuses the projection weights and it will be absorbed later so that the channel variances are lowered.

:rocket:OUROMAMBA

https://arxiv.org/abs/2503.10959

&emsp; Named after Ouroboros, they found a data-free post quantization method to quantize the Vision Mamba Models based on the calibration data which is actually synthesized by the model itself. Due to the forgetfulness nature of Mamba model, naively generate photos through VMMs result in noisy pictures. To compensate this, the authors propose an enhanced implicit attention mechanism which feels spatial information by aggregating neighbourhoods in patches around the anchor token in a weighted way, which is controlled by Δ, reflecting the information contained in each neighbouthood token. The second contribution is they dynamically detect outliers of activations and assign the different types of activation distribution (inliers & outlier) with mixed precision quantization accordingly on a regular refreshing rate, which leverage the time-vary nature of outliers across channels.

:rocket:PTQ4VM 
https://github.com/YoungHyun197/ptq4vm


:rocket:Bi-Mamba: Towards Accurate 1-Bit State Space Models
https://github.com/Tangshengku/Bi-Mamba

:rocket:Mamba-PTQ: Outlier Channels in Recurrent Large Language Models
https://arxiv.org/abs/2407.12397

&emsp; This artical is a preliminary attempt in the field of Mamba PTQ. They identify the existence of outlier channels in Mamba, which is the hard part to quantize, and try SmoothQuant to transfer part of the outliers in activation to weights.

:rocket:Post-Training Quantization for Vision Mamba with  k-Scaled Quantization and Reparameterization
https://arxiv.org/abs/2501.16738

&emsp; They compare similarity between FP layers and Quantizaed layers to determine a most similar scale from a pretrained search space. To deal with outliers, they use k-means clustering on both channel (perfroming good for convolutional layers) and token levels (performing good for linear projection layers because in these layers the outliers are little relationship with channels), enabling each group determined with a distinct scale to represent the outliers more accurately. Some hidden states of SSM have extreme large values, but the researchers find different channels share similar distributions. So they decompose the hidden states into three rank-1 vectors to approximate the hidden states. Finally, they smoothen h by converting the amplitude of original hidden states to A, B and C through "reparameterizing".

:rocket:Quamba
https://github.com/enyac-group/Quamba

## Structual Pruning
:rocket:Mamba-Shedder

https://github.com/IntelLabs/Hardware-Aware-Automated-Machine-Learning/tree/main/Mamba-Shedder

&emsp;Following method BlockPuner, which is used in Transformer (LLMs) structual pruning. They deploy experiments in Mamba-1, Mamba-2, Mamba+Transformer, and Hymba. They prune components and subcomponents in different architectures and explore various structural pruning strategies of different granularities.


🔥:BlockPruner:

https://github.com/MrGGLS/BlockPruner

&emsp;BlockPruner is a way to calculate the importance of blocks and remove the block with the lowest score iteratively in Transformer. It divides the Transformer architecture into multi-head attention (MHA) & multi-layer perceptron (MLP) blocks. It uses Perplexity as the importance metric tested in a sequence of words.


## Theory
🚀:MambaVC: Learned Visual Compression with Selective State Spaces

https://github.com/QinSY123/2024-MambaVC


🚀:The Hidden Attention of Mamba Models

https://github.com/AmeenAli/HiddenMambaAttn

&emsp; Very important essay to understand the attention mechnism in Mamba and SSM Structures. They derived a data-controlled attention matric from SSM formulas and explains the difference between Mamba and Transformer from attension perspective in detail. They demonstrate the application to Attention Rollout and Attention-based Attribution, which is also very useful in our work. Hotplots visualize the sequence dependencies of Mamba and Transformer in Vision and NLP tasks. But they only leverage the row of the final map associated with CLS token, maybe negelecting some useful information of other token interactions. Their perturbation experiments involve masking pixels, which can be another way of evaluating importance of tokens.

🚀:Explaining Modern Gated-Linear RNNs via a Unified Implicit Attention Formulation ICLR 2025

https://github.com/Itamarzimm/UnifiedImplicitAttnRepr/tree/main

&emsp; Following the last paper, this work contains more implementation work on sub-quadratic architectures with a proposed improved attention matrics. They implement perturbation tests for vision and NLP.

## Mamba Acceleration
:rocket:LightMamba: Efficient Mamba Acceleration on  FPGA with Quantization and Hardware Co-design
https://arxiv.org/abs/2502.15260

## Efficient Mamba
:rocket:MoE-Mamba: Efficient Selective State Space Models with Mixture of Experts

https://github.com/kyegomez/MoE-Mamba

&emsp;Following Switch Transformers and BlackMamba, they did a lot of experiments on Moe-Mamba, Vanilla Mamba, and Transformer-Moe.
"MoE-Mamba needs 2.35× fewer training steps to reach the same performance as Mamba."

🔥BlackMamba:

https://github.com/Zyphra/BlackMamba

&emsp;BlackMamba replaces "both the MLP layer in a transformer with an expert layer, and the attention layer with a mamba SSM layer."

🔥Switch Transformers

https://jmlr.org/papers/v23/21-0998.html




## Dynamic Network 
:rocket:DG-Mamba: Robust and Efficient Dynamic Graph Structure Learning with Selective State Space Models
https://github.com/haonan-yuan/DG-Mamba

:rocket:DyG-Mamba: Continuous State Space Modeling on Dynamic Graphs
https://arxiv.org/abs/2408.06966

:rocket:Learning Dynamic Brain Network Representation  Based on Graph Mamba Architecture (BIBM 2024)
https://github.com/tokamak-wang/brain-gm

## Application
:rocket:CleanUMamba: A Compact Mamba Network for  Speech Denoising using Channel Pruning
https://github.com/lab-emi/CleanUMamba

MambaMIM: Pre-training Mamba with State Space Token-interpolation




