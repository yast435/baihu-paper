# Baihu Paper

This repository tracks the LaTeX draft and supporting materials for the Baihu dataset paper.

## Working title

**Baihu: A Billion-Frame Multi-Embodiment Robot Manipulation Dataset for Embodied Foundation Models**

## Current paper direction

The current paper focuses on Baihu as a large-scale, multi-platform robot manipulation dataset for embodied foundation model pretraining and evaluation. The draft emphasizes:

- billion-frame robot pretraining data;
- multi-platform robot manipulation data coverage;
- task, scenario, and skill-level dataset characterization;
- HDF5-to-LeRobot v2.1 data standardization;
- offline open-loop zero-shot benchmark evaluation with GR00T N1.6.

## Repository structure

```text
paper/
  main.tex                         # Main LaTeX entry point
  body_main.tex                    # Abstract, introduction, related work, and dataset scale
  body_dataset_rest.tex            # Skill taxonomy, platform composition, scenarios, objects, and data format
  body_processing_benchmark.tex    # Data processing pipeline and benchmark experiments
  body_discussion.tex              # Discussion and limitations
  body_conclusion.tex              # Conclusion
  references.bib                   # Bibliography entries
  tables/                          # Dataset, skill taxonomy, platform, and benchmark tables

materials/                         # Source materials and experiment records
notes/                             # Notes and remaining tasks
```

## Main LaTeX build entry

The current paper draft should be built from:

```text
paper/main.tex
```

`main.tex` imports the paper body from the modular `body_*.tex` files and includes the task-level benchmark table in the appendix.

## Baihu facts used in the current draft

- Primary dataset version: `BAIHU_v2.0`
- Status: completed
- Duration: 9521.75 hours
- Tasks: 2989
- Episodes: 513575
- Frames: 1028349814
- Source format: HDF5
- Training format: LeRobot v2.1
- Robot platforms: 13
- Manipulation skills: 64

## Benchmark facts used in the current draft

- Model family: GR00T N1.6
- Baseline checkpoint: `checkpoint-1` no-training checkpoint
- Baihu-trained checkpoint: `checkpoint-390000` complete 1-epoch checkpoint trained on `BAIHU_v2.0`
- Evaluation type: offline open-loop zero-shot evaluation
- Evaluation scope: 13 platforms and 42 paired task-dataset records
- Overall ALL MSE reduction: 96.79%
- Overall Joint MSE reduction: 99.42%

## Important open issues

The final paper should still verify or refine:

1. the final data-source description for Baihu v2.0;
2. detailed platform descriptions for the 13 robot platforms;
3. dataset split definitions and release/access policy;
4. data quality control rules and filtering statistics;
5. formal citations and BibTeX entries for related datasets and model/tooling dependencies;
6. final figure/table captions and target submission formatting;
7. whether additional closed-loop, held-out-platform, or data-scaling experiments will be added.
