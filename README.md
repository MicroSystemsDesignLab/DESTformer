# DESTformer
DESTformer: Energy-Efficient Monocular Depth Estimation with Spiking Transformer for Edge Devices accepted in ICONS 2025

## Abstract
Monocular depth estimation is a crucial task in computer vision with numerous applications in autonomous driving, robotics, and augmented reality. 
Traditional methods often rely on frame-based approaches, which can be computationally expensive and lack efficiency in dynamic scenes. 
We propose a novel event-based monocular depth estimation framework, namely _DESTformer_, using spiking neural network (SNN) as the backbone architecture.
Our approach leverages the advantages of event-based cameras, which asynchronously capture pixel-level brightness changes (events) instead of traditional frames. 
These events are processed by a spiking transformer encoder that mimics the asynchronous and event-driven nature of the data. 
The spiking transformer extracts global features and generates sparse representations, which are then fed into the decoder for depth estimation refinement.
The SNN based encoder allows for efficient processing of event data while the transformer-based backbone maintains competitive accuracy in depth estimation. 
We demonstrate the effectiveness of our DESTformer model in an edge device - _Nvidia Jetson Orin Nano_, which allows up to $3.76\times$ speed up and $4.2\times$ lower energy consumption compared to existing methods opening up new possibilities for real-time depth estimation in dynamic environments, with implications for various applications in computer vision and robotics.

