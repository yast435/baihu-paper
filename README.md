# Baihu Paper

This repository tracks the Markdown draft and supporting materials for the Baihu dataset paper.

## Working title

**Baihu: A Billion-Frame Multi-Embodiment Robot Manipulation Dataset for Embodied Foundation Models**

## Current paper direction

Baihu v2.0 is framed as a large-scale, multi-embodiment robot manipulation dataset for embodied foundation model pretraining and evaluation. The current draft emphasizes:

- billion-frame robot pretraining data;
- multi-embodiment data distribution;
- HDF5-to-LeRobot v2.1 data standardization;
- dataset version management;
- offline zero-shot benchmark evaluation with GR00T N1.6.

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
  tables/                         # Dataset and benchmark tables
  figures/                        # Editable HTML/SVG figures
materials/                        # Source materials and experiment records
notes/
  todo.md                         # Remaining tasks and next steps
```

## Baihu v2.0 facts used in the current draft

- Version: `BAIHU_v2.0`
- Status: completed
- Duration: 9521.75 hours
- Tasks: 2989
- Episodes: 513575
- Frames: 1028349814
- Source format: HDF5
- Training format: LeRobot v2.1
- Embodiment tags: 14

## Benchmark facts used in the current draft

- Model family: GR00T N1.6
- Baseline checkpoint: `checkpoint-1` no-training checkpoint
- Baihu-trained checkpoint: `checkpoint-390000` complete 1-epoch checkpoint trained on BAIHU_v2.0
- Evaluation type: offline open-loop zero-shot evaluation
- Evaluation scope: 13 platforms and 42 paired task-dataset records
- Overall Joint MSE reduction: 99.42%
- Overall ALL MSE reduction: 96.79%

## Important open issues

The final paper should still verify or refine:

1. the final data-source description for Baihu v2.0;
2. platform descriptions for the 14 embodiment tags;
3. formal citations and BibTeX entries for related datasets;
4. final figure/table captions and target submission formatting;
5. whether additional closed-loop or scale-ablation experiments will be added.
