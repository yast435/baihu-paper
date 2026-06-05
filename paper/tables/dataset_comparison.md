# Table 6. Comparison with representative robot manipulation datasets

This table compares Baihu v2.0 with representative large-scale robot manipulation datasets and benchmarks. Public dataset numbers are listed according to the cited papers.

| Dataset | Real robot | Multi-embodiment | Scale | Tasks / Skills | Episodes / Trajectories | Format / Standardization | Main focus |
|---|---|---|---:|---:|---:|---|---|
| RoboMIND \cite{wu2024robomind} | Yes | Yes | 4 embodiments; hours not reported in the abstract | 479 tasks, 96 object classes | 107k demonstration trajectories | Unified collection platform and standardized protocol | Multi-embodiment manipulation benchmark with VLA evaluation |
| DROID \cite{khazatsky2024droid} | Yes | Limited / same robot setup across many sites | 350 hours, 564 scenes | 84 tasks | 76k demonstration trajectories | DROID dataset format and reproducible hardware setup | In-the-wild real-world manipulation data |
| Open X-Embodiment / RT-X \cite{oneill2023openx} | Yes | Yes | 22 robots from 21 institutions | 527 skills / 160,266 tasks | Large cross-robot data mixture | Standardized cross-embodiment data formats | X-robot policy learning and RT-X model training |
| BridgeData V2 \cite{walke2023bridgedatav2} | Yes | Limited / one low-cost robot platform | 24 environments | Multi-task manipulation behaviors | 60,096 trajectories | Dataset for goal-image and language-conditioned learning | Scalable robot learning across environments and tasks |
| **Baihu v2.0** | **Yes** | **Yes** | **9521.75 hours, 1.03B frames, 14 embodiment tags** | **2989 tasks** | **513,575 episodes** | **HDF5 source records converted to LeRobot v2.1** | **Billion-frame multi-embodiment data foundation for embodied foundation model pretraining and evaluation** |

Baihu uses `episode` terminology, while some prior datasets use `trajectory`. In this table, both refer to temporally ordered robot demonstration sequences. Baihu's distinguishing emphasis is the combination of billion-frame scale, multi-embodiment coverage, versioned data management, HDF5-to-LeRobot v2.1 standardization, and direct offline evaluation with GR00T N1.6 checkpoints.
