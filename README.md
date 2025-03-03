# RLPlanner-MF

2.5D integration has gained significant attention in recent years due to its cost-effectiveness and competitive performance. As the complexity and compactness of 2.5D systems increase, floorplanning becomes increasingly critical. This process must address open challenges such as microbump assignments, interconnect delays, and thermal limitations. This paper introduces RLPlanner-MF, an advanced floorplanning tool for 2.5D systems that integrates a novel fast thermal evaluation method, FastTM. RLPlanner-MF utilizes advanced reinforcement learning (RL) to simultaneously minimize total wirelength and peak temperature. To capture comprehensive information and generalize to unseen designs, RLPlanner-MF employs both a graph convolutional network (GCN) and a convolutional neural network (CNN) to preform multi-modal fusion. Moreover, RLPlanner-MF incorporates FastTM to expedite iterations and optimizations with rapid thermal evaluation. Extensive experiments demonstrate that FastTM achieves a mean absolute error (MAE) of ±0.41 K and delivers over 120$\times$ speedup in thermal evaluation compared to the open-source thermal solver Hotspot. RLPlanner-MF achieves an average improvement of 20.33\% in minimizing the target objective, with a speedup of 2.7$\times$ compared with the state-of-the-art methodology.
## Configurations
We use .cfg file to describe a 2.5D system. Here we briefly describe the options in the .cfg file.
### [chiplets]
- **chiplet_count**: the number of chiplets in the 2.5D system.
- **widths**: the width of each chiplet, separated by ",".
- **heights**: the height of each chiplet, separated by ",".
- **powers**: the power of each chiplet, separated by ",".
- **connections**: the connection matrix of chiplets. The i-th row and j-th column in the matrix is the bandwidth from chiplet i to chiplet j.

