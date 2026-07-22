---
name: "ML Supervised Regression Workflow"
description: "Run a supervised regression pipeline from CSV with EDA, preprocessing, training, evaluation, and documentation."
argument-hint: "Dataset path, target column, feature columns, instruction set"
agent: "agent"
---
Use the `ml-supervised-regression-workflow` skill for this task.

Implement and document a supervised regression project from CSV data.

Inputs:
- Dataset path: ${input:dataset_path}
- Workflow type (default regression): ${input:workflow_type}
- Target column: ${input:target_column}
- Feature columns: ${input:feature_columns}
- Optional test size (default 0.2): ${input:test_size}
- Optional random state (default 42): ${input:random_state}
- Optional instruction set (step-by-step rules from user): ${input:instruction_set}

Execution requirements:
1. Follow modular structure: data_loader.py, eda.py, preprocessing.py, model.py, main.py, README.md.
2. Include missing values, duplicates, outlier handling, and encoding decisions.
3. Train and evaluate with MAE, MSE, and R2.
4. Propose one step at a time and wait for approval before execution.
5. Keep branch-first workflow and provide PR-ready summary.
6. If workflow type or target behavior is classification, do not force regression; ask to switch to classification workflow.

If mandatory inputs are missing, ask concise clarification questions before implementation.
