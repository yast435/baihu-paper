# Baihu Paper TODO

## Highest priority

- [ ] Verify the final data-source description for Baihu v2.0.
  - Current ambiguity: internal model-demand data + Ant-delivered data vs. internal model-demand data + Dwheel-filtered data.
- [ ] Complete the 14-row embodiment distribution table.
  - Required columns: `embodiment_tag`, platform description, data source, tasks, episodes, frames, hours, hours_percent.
- [ ] Add task distribution statistics.
  - Number of tasks per embodiment.
  - Episodes per task.
  - Hours per task.
  - Long-tail task distribution.
- [ ] Document observation and action schemas.
  - Image modalities.
  - Robot state fields.
  - Action fields.
  - Language/task annotations.
- [ ] Define train/validation/test split.

## Dataset section

- [ ] Confirm all Baihu v2.0 numbers:
  - 9521.75 hours;
  - 2989 tasks;
  - 513575 episodes;
  - 1028349814 frames.
- [ ] Add exact LeRobot version and file schema.
- [ ] Add examples of episode structure.
- [ ] Add examples of task instructions.
- [ ] Add embodiment descriptions:
  - arx_loong;
  - astribots1;
  - cobotmagic;
  - dualur5e;
  - dwheel;
  - fr3;
  - genie1;
  - gr2;
  - lejukuaihu;
  - qinlongros1;
  - qinlongros2;
  - tianji;
  - xinghaitu_r1;
  - zhiyuana2.

## Figures

- [ ] Figure 1: Baihu data pipeline.
- [ ] Figure 2: embodiment duration distribution, preferably sorted horizontal bar chart rather than pie chart.
- [ ] Figure 3: task distribution.
- [ ] Figure 4: example trajectories / multi-view observations.
- [ ] Figure 5: benchmark overview.

## Tables

- [ ] Table 1: Baihu version comparison.
- [ ] Table 2: complete embodiment-level statistics.
- [ ] Table 3: comparison with RoboMIND, DROID, Open X-Embodiment, BridgeData V2, RH20T, AgiBot World.
- [ ] Table 4: benchmark results.
- [ ] Table 5: ablation results.

## Experiments

- [ ] Choose baseline models.
  - Candidate: GR00T N1.7.
  - Candidate: ACT.
  - Candidate: Diffusion Policy.
- [ ] Run open-loop action prediction.
- [ ] Report global metrics and per-embodiment metrics.
- [ ] Run data scale ablation: 10%, 25%, 50%, 100%.
- [ ] Run high-resource vs low-resource embodiment evaluation.
- [ ] Add real-world rollout results if available.

## Writing

- [ ] Expand Related Work with citations.
- [ ] Add dataset comparison table.
- [ ] Rewrite Abstract after experiment results are available.
- [ ] Convert Markdown draft to LaTeX when structure stabilizes.
