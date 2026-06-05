# Baihu Paper

This repository tracks the Markdown draft for the Baihu dataset paper.

## Working title

**Baihu: A Billion-Frame Multi-Embodiment Robot Manipulation Dataset for Embodied Foundation Models**

## Current paper direction

Baihu v2.0 is framed as a large-scale, multi-embodiment robot manipulation dataset for embodied foundation model pretraining and evaluation. The current draft emphasizes:

- large-scale robot pretraining data;
- multi-embodiment data distribution;
- LeRobot-compatible standardization;
- dataset version management;
- benchmark design for VLA / imitation-learning policies.

## Repository structure

```text
paper/
  main.md                         # Full paper draft entry point
  sections/
    01_introduction.md
    02_related_work.md
    03_dataset.md
    04_data_processing.md
    05_benchmark.md
    06_discussion.md
    07_conclusion.md
notes/
  todo.md                         # Missing information and next steps
```

## Baihu v2.0 facts used in the current draft

- Version: `BAIHU_v2.0`
- Status: completed
- Duration: 9521.75 hours
- Tasks: 2989
- Episodes: 513575
- Frames: 1028349814
- Format: LeRobot v2.1
- Embodiment tags: 14

## Important open issue

The source description for Baihu v2.0 still needs to be finalized. The current internal version document contains two slightly different descriptions:

1. model internal demand data + Ant-delivered data;
2. model internal demand data + Dwheel-filtered data.

The final paper should use one verified description.
