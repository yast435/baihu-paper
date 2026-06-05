# 5. Benchmark Design

To demonstrate the value of Baihu for embodied foundation model training, we evaluate whether a model trained on Baihu v2.0 improves offline action prediction on unseen tasks across multiple robot embodiments. The current benchmark focuses on open-loop zero-shot evaluation, where the model predicts actions from recorded observations and the predictions are compared against ground-truth actions in held-out trajectories.

## 5.1 Offline open-loop zero-shot evaluation

Open-loop evaluation provides an offline assessment by comparing the model's predicted actions against ground-truth actions from robot demonstration data. In this benchmark, we compare two GR00T N1.6 checkpoints:

| Checkpoint | Description |
|---|---|
| GR00T N1.6 / checkpoint-1 | No-training checkpoint, used as the baseline |
| GR00T N1.6 / checkpoint-390000 | Complete 1-epoch checkpoint trained on BAIHU_v2.0 |

The evaluation covers **13 embodiments / platforms** and **39 unseen tasks**. This setting is designed to measure whether Baihu v2.0 pretraining improves cross-task offline prediction performance without additional task-specific finetuning on the evaluation tasks.

## 5.2 Evaluation metrics

The benchmark reports two MSE metrics.

**ALL MSE** computes the mean squared error using all action dimensions available in the dataset. This metric reflects the model's full action prediction error, including arm, gripper, hand, or other action dimensions when they are present.

**Joint MSE** computes the mean squared error using only the joint-related action dimensions. Gripper or hand dimensions are excluded from this metric. This metric is useful because hand and gripper dimensions may have different scales, semantics, or sparsity patterns across embodiments, and may otherwise dominate or distort the action prediction error.

The evaluation follows the one-click batch open-loop evaluation workflow in `gr00t/batch_open_loop_eval.py`. The batch script evaluates combinations of checkpoints, embodiment tags, and datasets, generates statistics for each dataset, calls `gr00t/eval/open_loop_eval.py`, saves trajectory comparison plots, and writes average MSE results into a result table.

## 5.3 Current benchmark material

The current source material is stored in:

```text
materials/预训练离线实验记录表_测试记录数据总表_0430-同任务机型性能对比.xlsx
```

A structured summary of the experiment setting is maintained in:

```text
paper/tables/offline_zero_shot_eval_summary.md
```

The numerical results still need to be extracted from the Excel file and converted into paper-ready tables and figures.

## 5.4 Recommended result tables

The final paper should include at least the following result tables:

1. **Overall checkpoint comparison**: average ALL MSE and joint MSE for checkpoint-1 vs checkpoint-390000.
2. **Per-embodiment comparison**: average metrics for each of the 13 evaluated embodiments.
3. **Per-task comparison**: metrics for the 39 unseen tasks.
4. **Metric comparison**: ALL MSE vs joint-only MSE to show the influence of gripper / hand dimensions.
5. **Relative improvement**: percentage improvement from checkpoint-1 to checkpoint-390000.

## 5.5 Recommended figures

The benchmark section should include editable SVG / HTML figures generated from the extracted tables:

1. Bar chart of overall ALL MSE and joint MSE for checkpoint-1 vs checkpoint-390000.
2. Per-embodiment relative improvement plot.
3. Scatter plot comparing ALL MSE and joint MSE across tasks.
4. Sorted task-level improvement plot for the 39 unseen tasks.

## 5.6 Additional benchmark extensions

The current benchmark already provides a useful offline zero-shot comparison. Future versions can extend the benchmark with:

- data-scaling evaluation using different fractions of Baihu v2.0;
- high-resource vs low-resource embodiment evaluation;
- held-out embodiment evaluation;
- closed-loop simulation evaluation;
- real-world rollout success rate.
