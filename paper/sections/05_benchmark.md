# 5. Benchmark Experiments

To demonstrate the value of Baihu for embodied foundation model training, we evaluate whether a model trained on Baihu v2.0 improves offline action prediction on unseen tasks across multiple robot embodiments. The benchmark focuses on open-loop zero-shot evaluation, where the model predicts actions from recorded observations and the predictions are compared against ground-truth actions in held-out trajectories.

## 5.1 Offline open-loop zero-shot evaluation

Open-loop evaluation provides an offline assessment by comparing the model's predicted actions against ground-truth actions from robot demonstration data. In this benchmark, we compare two GR00T N1.6 checkpoints:

| Checkpoint | Description |
|---|---|
| GR00T N1.6 / checkpoint-1 | No-training checkpoint, used as the baseline |
| GR00T N1.6 / checkpoint-390000 | Complete 1-epoch checkpoint trained on BAIHU_v2.0 |

The evaluation covers **13 embodiments / platforms** and **42 paired task-dataset records**. This setting is designed to measure whether Baihu v2.0 pretraining improves cross-task offline prediction performance without additional task-specific finetuning on the evaluation tasks.

## 5.2 Evaluation metrics

The benchmark reports two MSE metrics.

**ALL MSE** computes the mean squared error using all action dimensions available in the dataset. This metric reflects the model's full action prediction error, including arm, gripper, hand, or other action dimensions when they are present.

**Joint MSE** computes the mean squared error using only the joint-related action dimensions. Gripper or hand dimensions are excluded from this metric. This metric is useful because hand and gripper dimensions may have different scales, semantics, or sparsity patterns across embodiments, and may otherwise dominate or distort the action prediction error.

The evaluation follows the one-click batch open-loop evaluation workflow in `gr00t/batch_open_loop_eval.py`. The batch script evaluates combinations of checkpoints, embodiment tags, and datasets, generates statistics for each dataset, calls `gr00t/eval/open_loop_eval.py`, saves trajectory comparison plots, and writes average MSE results into a result table.

## 5.3 Overall results

The current source material is stored in:

```text
materials/预训练离线实验记录表_测试记录数据总表_0430-同任务机型性能对比.csv
```

The corrected benchmark table shows that one epoch of training on BAIHU_v2.0 substantially reduces offline open-loop prediction error across the 13 evaluated platforms and 42 paired task-dataset records.

| Model checkpoint | Joint MSE ↓ | ALL MSE ↓ |
|---|---:|---:|
| checkpoint-1 (no training) | 0.116746 | 0.157283 |
| checkpoint-390000 (Baihu v2.0, 1 epoch) | 0.000680 | 0.005051 |
| Relative improvement | 99.42% | 96.79% |

The complete overall result table is maintained in:

```text
paper/tables/offline_zero_shot_eval_overall.md
```

## 5.4 Per-platform results

Because Baihu v2.0 is a multi-embodiment dataset, aggregate metrics alone are insufficient. We therefore also report per-platform results. After correcting the reversed `智元G1 / 电源组件安装` row in the source CSV, all 13 evaluated platforms show positive improvement in both Joint MSE and ALL MSE.

The complete per-platform result table is maintained in:

```text
paper/tables/offline_zero_shot_eval_by_machine.md
```

## 5.5 Task-level analysis

Task-level metrics are maintained in:

```text
paper/tables/offline_zero_shot_eval_by_task.md
```

These records can be used to identify tasks with unusually high residual error after Baihu training, tasks with the largest relative improvement, and possible data or evaluation inconsistencies.

## 5.6 Figures

Editable HTML/SVG figures for the benchmark are maintained in:

```text
paper/figures/offline_zero_shot_eval_editable.html
```

The recommended paper figures are:

1. Bar chart of overall ALL MSE and Joint MSE for checkpoint-1 vs checkpoint-390000.
2. Per-platform relative improvement plot.
3. Scatter plot comparing ALL MSE and Joint MSE across tasks.
4. Sorted task-level improvement plot for the 42 paired task-dataset records.

## 5.7 Additional benchmark extensions

The current benchmark already provides a useful offline zero-shot comparison. Future versions can extend the benchmark with:

- data-scaling evaluation using different fractions of Baihu v2.0;
- high-resource vs low-resource embodiment evaluation;
- held-out embodiment evaluation;
- closed-loop simulation evaluation;
- real-world rollout success rate.
