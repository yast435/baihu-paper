# 2. Related Work

## Robot manipulation datasets

Large-scale robot datasets have become increasingly important for training generalist robot policies. Existing datasets such as RoboMIND, DROID, BridgeData V2, and Open X-Embodiment provide diverse robot manipulation trajectories and have demonstrated the value of large-scale data for imitation learning and policy generalization. RoboMIND focuses on multi-embodiment robot manipulation and provides real-world demonstrations across diverse tasks and object categories. DROID emphasizes in-the-wild robot manipulation across many real environments. Open X-Embodiment aggregates robot data from multiple institutions and embodiments to study cross-robot policy learning.

Baihu follows the same general direction of building large-scale robot data for embodied intelligence, but differs in its focus on pretraining-scale dataset construction, versioned data management, and standardized LeRobot-compatible organization. Instead of targeting only a fixed benchmark suite, Baihu is designed as a continuously expandable data foundation for training and evaluating robot foundation models.

## Vision-language-action models

Vision-language-action models aim to map visual observations and language instructions to robot actions. These models require datasets that contain synchronized visual observations, robot states, actions, and task descriptions. The quality and diversity of the training data directly affect the model's ability to generalize across tasks and environments. Baihu is designed to support this training paradigm by organizing robot trajectories into standardized observation-action sequences and task-level annotations.

## Data standardization for robot learning

Robot data is inherently heterogeneous. Different robots may use different action spaces, control frequencies, camera configurations, gripper definitions, and state representations. Without standardization, it is difficult to train a unified policy across multiple data sources. Baihu addresses this challenge by adopting a unified data format and maintaining explicit dataset versions. The versioned design makes it possible to track data fixes, normalization changes, and newly integrated data sources across different releases.

## To be expanded

This section still needs a complete comparison table against prior datasets, including at least:

- RoboMIND;
- DROID;
- Open X-Embodiment / RT-X;
- BridgeData V2;
- RH20T;
- AgiBot World;
- LIBERO, if benchmark comparison is needed.
