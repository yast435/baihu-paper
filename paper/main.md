# Baihu: A Billion-Frame Multi-Embodiment Robot Manipulation Dataset for Embodied Foundation Models

## Abstract

Large-scale, diverse, and standardized robot manipulation data is becoming a critical foundation for training embodied intelligence models and generalist robot policies. However, existing robot datasets often suffer from limited task diversity, inconsistent data formats, restricted embodiment coverage, or insufficient scale for pretraining large vision-language-action models. In this work, we introduce **Baihu v2.0**, a large-scale robot manipulation dataset designed for embodied foundation model pretraining and evaluation. Baihu v2.0 contains **9521.75 hours** of robot data, covering **2989 tasks**, **513575 episodes**, and over **1.03 billion frames**. The dataset integrates multi-source robot operation data curated for model training and is standardized into the LeRobot format to support scalable policy learning.

Baihu is designed not only as a data repository, but also as a pretraining-scale infrastructure for robot learning. It provides a unified organization of robot trajectories, task annotations, observation-action sequences, and metadata, enabling downstream training of imitation-learning policies and vision-language-action models. We further outline a benchmark protocol for evaluating robot foundation models on Baihu, including open-loop action prediction, data-scaling analysis, task-level generalization, and downstream policy evaluation.

## 1. Introduction

See [`sections/01_introduction.md`](sections/01_introduction.md).

## 2. Related Work

See [`sections/02_related_work.md`](sections/02_related_work.md).

## 3. Baihu Dataset

See [`sections/03_dataset.md`](sections/03_dataset.md).

## 4. Data Processing Pipeline

See [`sections/04_data_processing.md`](sections/04_data_processing.md).

## 5. Benchmark Design

See [`sections/05_benchmark.md`](sections/05_benchmark.md).

## 6. Discussion and Limitations

See [`sections/06_discussion.md`](sections/06_discussion.md).

## 7. Conclusion

See [`sections/07_conclusion.md`](sections/07_conclusion.md).

## Draft status

This is a v0.1 Markdown draft. Several details remain placeholders and must be verified before submission, especially data sources, robot embodiment descriptions, modalities, train/validation/test splits, and benchmark results.
