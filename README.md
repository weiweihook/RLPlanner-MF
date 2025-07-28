# RLPlanner-MF

 As the complexity and compactness of 2.5D systems increase, floorplanning encounters challenges such as thermal-interconnect tradeoff, thermal computation, and efficiency. To address these issues, we present RLPlanner-MF, an advanced floorplanning tool for 2.5D systems. RLPlanner-MF incorporates FastTM, a novel thermal evaluation method that significantly accelerates computation, and a chiplet-ordering algorithm to optimize chiplet placement sequence. Leveraging reinforcement learning (RL), RLPlanner-MF jointly optimizes total wirelength and peak temperature. To enhance generalization across unseen designs, it adopts a multi-modal fusion approach, combining a Graph Convolutional Network (GCN) with a Convolutional Neural Network (CNN). Extensive experiments show that FastTM achieves a 120× speedup in thermal evaluations compared to Hotspot, while maintaining high accuracy. RLPlanner-MF delivers an average 20.33\% improvement in the target objective and provides a 2.7$\times$ speedup over state-of-the-art methods.

## Benchmarks
<img src="https://github.com/weiweihook/RLPlanner-MF/blob/main/benchmark.png" width="600"/>

## Hypeparameters
<center>
  
| Hyperparameter | Value |
| :-------------------------:|:-------------------------: |
| Activation Function | ReLU|
| Optimizer           | Adam |
| Learning Rate       | 2.5E-4 |
| Parallel environment (n_e)       | 64/128/256 |
| Batch Size          | n_e * len(episode) |
| Clip Gradient Norm  | 0.5 |
| Total Epoch         | 500 |
| Clipping Coefficient| 0.1 |
| Entropy Coefficient | 0.01|
| Value Coefficient   | 0.5 |
| Discount(γ)         | 0.99|
  
</center>

*The length of each episode depends on the number of chiplets.



## Configurations
We use .cfg file to describe a 2.5D system. Here we briefly describe the options in the .cfg file.
### [chiplets]
- **chiplet_count**: the number of chiplets in the 2.5D system.
- **widths**: the width of each chiplet, separated by ",".
- **heights**: the height of each chiplet, separated by ",".
- **powers**: the power of each chiplet, separated by ",".
- **connections**: the connection matrix of chiplets. The i-th row and j-th column in the matrix is the bandwidth from chiplet i to chiplet j.
- **u**: the graph node 'i'.
- **v**: the graph node 'j'.
- **e**: the connection wires between node 'i' and 'j'.

