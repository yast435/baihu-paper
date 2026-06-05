# 7. Conclusion

We introduced **Baihu v2.0**, a billion-frame, multi-embodiment robot manipulation dataset for embodied foundation model pretraining and evaluation. Baihu v2.0 contains **9521.75 hours** of robot data, **2989 tasks**, **513575 episodes**, and **1028349814 frames** across **14 embodiment tags**. The dataset converts multi-source HDF5 robot operation records into the LeRobot v2.1 format, providing a standardized data foundation for training vision-language-action models and generalist robot policies.

Baihu v2.0 is not only large in scale, but also diverse across robot embodiment tags, task types, objects, and temporal horizons. Its long-tailed embodiment distribution makes it suitable for studying both high-resource policy learning and low-resource cross-embodiment generalization.

We further evaluated the utility of Baihu v2.0 through offline open-loop zero-shot evaluation with GR00T N1.6. Across **13 platforms** and **42 paired task-dataset records**, a checkpoint trained on Baihu v2.0 for one epoch reduced **Joint MSE by 99.42%** and **ALL MSE by 96.79%** compared with a no-training checkpoint. These results suggest that Baihu v2.0 provides effective large-scale supervision for robot action prediction and can serve as practical infrastructure for future embodied foundation model development.

Future work will extend Baihu with additional versions, broader benchmark protocols, more baseline models, closed-loop evaluations, and clearer release documentation. Together, these directions can further strengthen Baihu as a reusable data foundation for large-scale embodied intelligence research.
