# 4. Data Processing Pipeline

Baihu is constructed through a multi-stage data processing pipeline. The goal of this pipeline is to convert heterogeneous raw robot data into a consistent and trainable format.

First, raw robot trajectories are collected or integrated from different data sources. Each trajectory is associated with task information and robot operation records. Second, data validation is performed to remove incomplete, corrupted, or invalid episodes. Third, robot states and actions are converted into unified representations. Fourth, embodiment-specific fields such as gripper or effector ranges are normalized to ensure consistency across different subsets. Finally, the processed data is converted into the LeRobot format and registered under a versioned dataset release.

The version history of Baihu shows that earlier releases corrected issues such as inconsistent effector mapping ranges and gripper value reconstruction. This highlights the importance of versioned data management for robot learning datasets. Small inconsistencies in action normalization or gripper mapping can significantly affect model training, especially when the dataset is used for large-scale policy pretraining.

## 4.1 Raw data ingestion

Raw data is integrated from multiple robot data sources. The exact raw formats and source-specific fields should be documented here.

**To be filled:**

- raw data formats;
- source directory structure;
- robot-specific metadata;
- original control frequencies;
- camera streams and resolutions;
- language or task annotation source.

## 4.2 Trajectory validation

Trajectory validation is used to filter incomplete or invalid episodes before model training. The final paper should describe the validation rules explicitly.

**To be filled:**

- minimum episode length;
- missing frame handling;
- corrupted image handling;
- invalid action/state detection;
- task label validation;
- duplicate episode removal.

## 4.3 State and action normalization

Because Baihu integrates multiple robot embodiments, state and action representations must be normalized or standardized before training. Earlier Baihu versions fixed effector mapping range inconsistencies and gripper value reconstruction issues, suggesting that state/action normalization is a central part of the dataset pipeline.

**To be filled:**

- action space definitions by embodiment;
- state space definitions by embodiment;
- gripper / effector mapping rules;
- clipping ranges;
- normalization and de-normalization formulas;
- treatment of missing fields.

## 4.4 LeRobot conversion

After validation and normalization, data is converted into the LeRobot-compatible format. The final paper should describe the generated files, metadata schema, and loading process.

**To be filled:**

- LeRobot version;
- episode file layout;
- `tasks.jsonl` schema;
- `info.json` schema;
- `stats.json` schema;
- video storage format;
- train/validation/test split files.
