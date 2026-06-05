# Dataset comparison table

This table compares Baihu v2.0 with representative large-scale robot manipulation datasets and benchmarks. Public dataset numbers should be verified again before final submission.

| Dataset | Real robot | Multi-embodiment | Scale | Tasks / Skills | Episodes / Trajectories | Format / Standardization | Main focus |
|---|---|---|---:|---:|---:|---|---|
| RoboMIND | Yes | Yes | Not reported as hours | 479 tasks, 96 object classes | 107k demonstration trajectories | Unified collection platform and protocol | Multi-embodiment manipulation benchmark with VLA evaluation |
| DROID | Yes | Limited / same robot setup across many sites | 350 hours, 564 scenes | 84 tasks | 76k demonstration trajectories | DROID dataset format and reproducible hardware setup | In-the-wild real-world manipulation data |
| Open X-Embodiment / RT-X | Yes | Yes | 22 robots from 21 institutions | 527 skills / 160,266 tasks | Large cross-robot data mixture | Standardized cross-embodiment data formats | X-robot policy learning and RT-X model training |
| BridgeData V2 | Yes | Limited | 24 environments | Multi-task manipulation behaviors | 60,096 trajectories | Dataset for goal-image and language-conditioned learning | Scalable robot learning across environments and tasks |
| **Baihu v2.0** | **Yes** | **Yes** | **9521.75 hours, 1.03B frames** | **2989 tasks** | **513,575 episodes** | **LeRobot v2.1-compatible organization** | **Billion-frame multi-embodiment data foundation for embodied foundation model pretraining and evaluation** |

## Notes

- Baihu v2.0 is compared using its completed v2.0 version statistics.
- Baihu uses `episode` terminology, while some prior datasets use `trajectory`. In this table, both refer to temporally ordered robot demonstration sequences.
- Baihu's distinguishing emphasis is the combination of billion-frame scale, multi-embodiment coverage, versioned data management, LeRobot-compatible standardization, and direct offline evaluation with GR00T N1.6 checkpoints.
