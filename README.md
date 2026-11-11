# SSTCF-UAV: Sparse Spatio-Temporal Coarse-to-Fine UAV Detection

**A LiDAR-only framework for detecting and localizing small UAVs in sparse point-cloud scenes.**

[Overview](#overview) · [Architecture](#architecture) · [Public dataset](#public-dataset) · [Code availability](#code-availability)

> **Code will be publicly released upon acceptance of the paper.**

## Overview

SSTCF-UAV combines current-frame geometry with historical spatiotemporal occupancy to localize small UAVs across a large search space. Its coarse-to-fine design first identifies a promising region, then refines the target center using high-resolution local features and coarse-stage context.

The framework brings together:

- **Joint spatial and temporal encoding** to represent current-frame geometry and the persistence of sparse returns across successive scans.
- **Gaussian mixture prediction and local probability-mass routing** to select a region for fine localization.
- **Context-guided refinement** to combine local geometry with coarse-stage features.
- **A local geometric height anchor** to support accurate vertical localization.

## Architecture

![SSTCF-UAV architecture](docs/assets/architecture.png)

*Current-frame sparse geometry (SGE) and spatiotemporal occupancy (STOE) are fused by GSTF. The Gaussian mixture prediction head (GMPH) routes a local region to context-guided localization refinement (CGLR). The detector returns the current-frame UAV center and confidence in the input LiDAR coordinate system.*

## Public dataset

The project uses the **[Multi-LiDAR Multi-UAV Dataset](https://tiers.github.io/multi_lidar_multi_uav_dataset/)** released by the University of Turku's TIERS team, with separate configurations for **Livox Avia**, **Livox MID-360**, and **Ouster OS1-64**.

For point-cloud annotation, see the **[LiDAR Trajectory Label Tool](https://github.com/Hsief/lidar-trajectory-label-tool)**.

## Code availability

The source code and sensor-specific configurations will be publicly released in this repository upon acceptance of the paper. The release will include instructions for data preparation, training, and inference.

## Dataset reference

```bibtex
@inproceedings{catalano2023towards,
  title={Towards Robust UAV Tracking in GNSS-Denied Environments:
         A Multi-LiDAR Multi-UAV Dataset},
  author={Catalano, Iacopo and Yu, Xianjia and Queralta, Jorge Pe\~na},
  booktitle={2023 IEEE International Conference on Robotics and Biomimetics (ROBIO)},
  pages={1--7},
  year={2023},
  organization={IEEE}
}
```
