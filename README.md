# Kneron AI Training/Deployment Platform (mmpose-based)


## Introduction

---
  [kneron-mmpose](https://github.com/kneron/kneron-mmpose) is a platform built upon the well-known [mmpose](https://github.com/open-mmlab/mmpose) for pose estimation . We encourage that you may start with the [rsn18_hand_pose_step_by_step.md](https://github.com/kneron/kneron-mmpose/blob/update_document/docs_kneron/rsn18_hand_step_by_step.md) to build basic knowledge of Kneron-Edition MMPose, and read [mmpose docs](https://mmpose.readthedocs.io/en/v0.25.0/) for detailed mmpose usage.  

  In this repository, we provide an end-to-end training/deployment flow to realize on Kneron's AI accelerators:

  1. **Training/Evalulation:**
      - Modified model configuration and verified for Kneron hardware platform
      - Please see [Overview of Benchmark and Model Zoo](#Overview-of-Benchmark-and-Model-Zoo) for the model list
  2. **Converting to onnx:**
      - pytorch2onnx_kneron.py (beta)
      - Export *optimized* and *Kneron-toolchain supported* onnx
          - Automatically modify model for arbitrary data normalization preprocess
  3. **General Evaluation**
      - tools/test_kneron.py (beta)
      - Evaluate the model with *pytorch checkpoint, onnx, and kneron-nef*
  4. **Testing**
      - inference_kn (beta)
      - Verify the converted [NEF](http://doc.kneron.com/docs/#toolchain/manual/#5-nef-workflow) model on Kneron USB accelerator with this API
  5. **Converting Kneron-NEF:** (toolchain feature)
     - Convert the trained pytorch model to [Kneron-NEF](http://doc.kneron.com/docs/#toolchain/manual/#5-nef-workflow) model, which could be used on Kneron hardware platform.

## License

This project is released under the [Apache 2.0 license](LICENSE).

## Changelog

N/A

## Overview of Benchmark and Kneron Model Zoo
| Backbone  | size   | Mem (GB) | AUC | PCK | EPE | Config | Download |
|:---------:|:-------:|:-------:|:-------:|:-------:|:-------:|:--------:|:------:|
| rsn18 | 224 |   0.014   |   0.855  | 0.987 | 3.687 | [config](https://github.com/kneron/kneron-mmpose/blob/main/configs/hand/2d_kpt_sview_rgb_img/topdown_heatmap/freihand2d/rsn18_freihand2d_224x224.py)       |[model]((https://github.com/kneron/Model_Zoo/tree/main/mmpose/rsn18_freihand)

## Installation
- Please refer to [get_started.md](docs/en/get_started.md) for installation.
- Please refer to [Kneron PLUS - Python: Installation](http://doc.kneron.com/docs/#plus_python/introduction/install_dependency/) for the environment setup for Kneron USB accelerator.

## Getting Started
### Tutorial - Kneron Edition
- [rsn18_hand_pose_step_by_step.md](https://github.com/kneron/kneron-mmpose/blob/update_document/docs_kneron/rsn18_hand_step_by_step.md): A tutorial for users to get started easily. To see detailed documents, please see below.

### Documents - Kneron Edition
- [Kneron ONNX Export] (under development)
- [Kneron Inference] (under development)
- [Kneron toolchain step-by-step (YOLOv3)](http://doc.kneron.com/docs/#toolchain/yolo_example/)
- [Kneron toolchain manual](http://doc.kneron.com/docs/#toolchain/manual/#0-overview)

### Original mmpose Documents
- [original mmpose getting started](https://github.com/open-mmlab/mmpose/blob/master/docs/en/getting_started.md): It is recommended to read original MMXXXX getting started documents for other mmpose operations.
- [original mmpose readthedoc](https://mmpose.readthedocs.io/en/v0.25.0/): Original mmpose documents.

## Contributing
---
[kneron-mmpose](https://github.com/kneron/kneron-mmpose) a platform built upon [OpenMMLab-mmpose](https://github.com/open-mmlab/mmpose)

- For issues regarding to the original [mmpose](https://github.com/open-mmlab/mmpose):
We appreciate all contributions to improve [OpenMMLab-mmpose](https://github.com/open-mmlab/mmpose). Ongoing projects can be found in out [GitHub Projects](https://github.com/open-mmlab/mmpose/projects?type=beta). Welcome community users to participate in these projects. Please refer to [CONTRIBUTING.md](.github/CONTRIBUTING.md) for the contributing guideline.

- For issues regarding to this repository [kneron-mmpose](https://github.com/kneron/kneron-mmpose): Welcome to leave the comment or submit the pull request here to improve kneron-mmpose


## Related Projects
- [kneron-mmdetection](https://github.com/kneron/kneron-mmdetection): Kneron training/deployment platform on [OpenMMLab - mmdetection](https://github.com/open-mmlab/mmdetection) object detection toolbox
