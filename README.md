# Mamba-Compression-Acceleration-Efficient-papers
## Mamba Compression

### Token reduction
R-MeeTo 
https://github.com/NUS-HPC-AI-Lab/R-MeeTo
  Token merging + Re-training
  Inspired by ToMe, in the token merging stage, this paper first divides tokens into odd and even sequence, then calculate their distance, and finally merge the most relevent r pairs. The Retraining stage extremely quickly restore the accuracy of the token merged model.

Famba-V （ECCV 2024）
https://github.com/AIoT-MLSys-Lab/Famba-V
Also based on ToMe, this paper proposes a suit of cross-layer choice strategies in Vim.

Exploring Token Pruning in Vision State Space Models
https://github.com/ZLKong/ToP-ViM

Rethinking Token Reduction for State Space Models
https://github.com/wuyushuwys/ToR_SSM

### Quantization
OUROMAMBA
https://arxiv.org/abs/2503.10959

PTQ4VM 
https://github.com/YoungHyun197/ptq4vm


Bi-Mamba: Towards Accurate 1-Bit State Space Models
https://github.com/Tangshengku/Bi-Mamba

Mamba-PTQ: Outlier Channels in Recurrent Large Language Models
https://arxiv.org/abs/2407.12397

Post-Training Quantization for Vision Mamba with  k-Scaled Quantization and Reparameterization
https://arxiv.org/abs/2501.16738

Quamba
https://github.com/enyac-group/Quamba


### Structual Pruning
Mamba-Shedder
https://github.com/IntelLabs/Hardware-Aware-Automated-Machine-Learning/tree/main/Mamba-Shedder




## Mamba Acceleration
LightMamba: Efficient Mamba Acceleration on  FPGA with Quantization and Hardware Co-design
https://arxiv.org/abs/2502.15260

## Efficient Mamba
MoE-Mamba: Efficient Selective State Space Models with Mixture of Experts
https://github.com/kyegomez/MoE-Mamba

## Dynamic Network 
DG-Mamba: Robust and Efficient Dynamic Graph Structure Learning with Selective State Space Models
https://github.com/haonan-yuan/DG-Mamba

DyG-Mamba: Continuous State Space Modeling on Dynamic Graphs
https://arxiv.org/abs/2408.06966

Learning Dynamic Brain Network Representation  Based on Graph Mamba Architecture (BIBM 2024)
https://github.com/tokamak-wang/brain-gm

## Application
CleanUMamba: A Compact Mamba Network for  Speech Denoising using Channel Pruning
https://github.com/lab-emi/CleanUMamba

MambaMIM: Pre-training Mamba with State Space Token-interpolation
