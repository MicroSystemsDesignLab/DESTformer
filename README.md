# DESTformer
DESTformer: Energy-Efficient Monocular Depth Estimation with Spiking Transformer for Edge Devices accepted in [ICONS 2025](https://iconsneuromorphic.cc/)

## Abstract
Monocular depth estimation is a crucial task in computer vision with numerous applications in autonomous driving, robotics, and augmented reality. 
Traditional methods often rely on frame-based approaches, which can be computationally expensive and lack efficiency in dynamic scenes. 
We propose a novel event-based monocular depth estimation framework, namely _DESTformer_, using spiking neural network (SNN) as the backbone architecture.
Our approach leverages the advantages of event-based cameras, which asynchronously capture pixel-level brightness changes (events) instead of traditional frames. 
These events are processed by a spiking transformer encoder that mimics the asynchronous and event-driven nature of the data. 
The spiking transformer extracts global features and generates sparse representations, which are then fed into the decoder for depth estimation refinement.
The SNN based encoder allows for efficient processing of event data while the transformer-based backbone maintains competitive accuracy in depth estimation. 
We demonstrate the effectiveness of our DESTformer model in an edge device - _Nvidia Jetson Orin Nano_, which allows up to $3.76\times$ speed up and $4.2\times$ lower energy consumption compared to existing methods opening up new possibilities for real-time depth estimation in dynamic environments, with implications for various applications in computer vision and robotics.

## Dataset
[MVSEC](https://daniilidis-group.github.io/mvsec/)
[DENSE](https://rpg.ifi.uzh.ch/E2DEPTH.html)

## Training

```bash
CUDA_VISIBLE_DEVICES=0 python3 main.py --epochs 70 --batch_size 8 --num_enc_dec_layers 12 --lr 0.0003
```
## Testing
Testing is done in two steps. First, is to run test.py script, which saves the prediction outputs in a folder. 
```bash
CUDA_VISIBLE_DEVICES=0 python test.py --path_to_model experiments/exp_1/checkpoints/model_best.pth.tar --output_folder experiments/exp_1/test/ --data_folder test 
```
Later, we run evaluation.py script takes both the groundtruth and prediction output as inputs, and calculates the metric depth on logarithmic depth maps using both clip distance and reg_factor. 
