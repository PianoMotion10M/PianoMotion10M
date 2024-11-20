<div align="center">
<h1><img src="assets/favicon.png" width="50"> PianoMotion10M </h1>
<h3>Dataset and Benchmark for Hand Motion Generation in Piano Performance</h3>

Anonymous authors

Paper under double-blind review

</div>

## Abstract

Recently, artificial intelligence techniques for education have been received increasing attentions, while it still remains an open problem to design the effective music instrument instructing systems. Although key presses can be directly derived from sheet music, the transitional movements among key presses require more extensive guidance in piano performance. In this work, we construct a piano-hand motion generation benchmark to guide hand movements and fingerings for piano playing. To this end, we collect an annotated dataset, PianoMotion10M, consisting of 116 hours of piano playing videos from a bird's-eye view with 10 million annotated hand poses. We also introduce a powerful baseline model that generates hand motions from piano audios through a position predictor and a position-guided gesture generator. Furthermore, a series of evaluation metrics are designed to assess the performance of the baseline model, including motion similarity, smoothness, positional accuracy of left and right hands, and overall fidelity of movement distribution. Despite that piano key presses with respect to music scores or audios are already accessible, PianoMotion10M aims to provide guidance on piano fingering for instruction purposes.

## Introduction
<div align="center"><h4>PianoMotion10M is a large-scale piano-motion dataset. And we present a benchmark for hand motion generation with piano music.</h4></div>

![framework](assets/teaser.png "framework")

Overview of our framework. We collect videos of expert piano performances from the internet and annotated and processed them to obtain a large-scale dataset, PianoMotion10M, comprising piano music and hand motions. Building upon this dataset, we establish a benchmark aimed at generating hand movements from piano music.

## Models

> Sample results of our generation model.

https://github.com/user-attachments/assets/f346608b-cfe3-4984-a39a-c8ae5794f7bf

https://github.com/user-attachments/assets/1bed9659-a88d-4b84-8a16-f787ad0de822

https://github.com/user-attachments/assets/8860cf2e-1146-45ca-8d96-59ac161fdc03



> Results from the PianoMotion10M

![comparison](assets/comparison.png "comparison")

|    Method     |  Backbone  |   Decoder   |  FID  | PARAMs |
|:-------------:|:----------:|:-----------:|:-----:|:------:| 
|    EmoTalk    |   HuBert   | Transformer | 4.645 |  308   |
| LivelySpeaker |   HuBert   | Transformer | 4.157  |  321   |
|   Our-Base    | Wav2Vec2.0 |     SSM     | 3.587 |  320   |
|   Our-Base    |   Wav2Vec2.0   | Transformer | 3.608 |  323   |
|   Our-Base    | HuBert |     SSM     | 3.412 |  320   |
|   Our-Base    |   HuBert   | Transformer | 3.529 |  323   |
|   Our-Large   |   Wav2Vec2.0   |     SSM     | 3.453  |  539   |
|   Our-Large   |   Wav2Vec2.0   | Transformer | 3.376 |  557   |
|   Our-Large   |   HuBert   |     SSM     | 3.395  |  539   |
|   Our-Large   |  HuBert   | Transformer | **3.281** |  557   |

> Sample results generated with MIDI guidance.


https://github.com/user-attachments/assets/2f43d7a0-e220-45e1-aa99-80c31d7e1dde


https://github.com/user-attachments/assets/fc45a2f5-2119-4364-9707-35c1a23cbddd




**Notes**: 

- All the experiments are performed on 1 NVIDIA GeForce RTX 3090Ti GPU.


## Getting Started
- [Installation](docs/install.md)
- [Prepare Dataset](docs/prepare_dataset.md)
- [Train and Eval](docs/train_eval.md)
