# Gold Testset Plan: Multi-classification-identification-of-medical-dermatology
> Generated: 2026-06-08  
> Tier: A-core  
> Project bucket: Medical computer vision / classification  
> Priority score: 89  
> GitHub: https://github.com/DavidZhu258/Multi-classification-identification-of-medical-dermatology

## Evaluation Goal

验证皮肤病多分类和黑色素瘤识别在不泄漏患者/来源的情况下是否可靠。

## Target Gold Set

- Target size: **1000+ images**
- Eval type: `cv_classification`
- Seed cases created now: **3**
- First next step from matrix: 固定无泄漏 split，输出 confusion matrix + melanoma one-vs-rest AUC。

## Test-set Design

公开皮肤病数据集 holdout：按患者/来源切分；类别均衡、长尾类别、疑难黑色素瘤样本。

## Metrics

Accuracy metrics:

```text
macro F1; balanced accuracy; AUC; melanoma sensitivity/specificity; calibration ECE; confusion matrix; external validation
```

Feasibility metrics:

```text
reproducible training; inference latency; class imbalance handling; model card; clinical caution disclaimers
```

Rubric seed metrics:

- macro_f1
- balanced_accuracy
- auc
- melanoma_sensitivity
- specificity
- calibration_ece

## Required Hard Cases

类别不均衡、相似病灶、图像质量差、训练/测试来源泄漏、过度自信误诊。

## Build Plan

1. Replace the 3 placeholder seed cases in `evals/gold/seed_gold.jsonl` with real examples.
2. Fill `evals/gold/annotation_template.csv` with expected labels, evidence references, and reviewer status.
3. Run a manual seed evaluation and save raw output in `evals/results/`.
4. Only after the seed suite is stable, expand `evals/gold/full_gold.jsonl` toward the target size.
5. Publish evidence only when the report includes both accuracy and feasibility metrics.

## Acceptance Bar

For portfolio use, the project must pass all seed hard negatives, have a reproducible fresh-run path, and show at least one saved result artifact under `evals/results/`.

## Evidence to Add

模型卡、数据卡、混淆矩阵、校准图、失败案例。
