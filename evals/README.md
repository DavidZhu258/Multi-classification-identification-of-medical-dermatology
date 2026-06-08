# evals/ for Multi-classification-identification-of-medical-dermatology

Minimum evaluation scaffold for `Multi-classification-identification-of-medical-dermatology`.

## Layout

```text
evals/
  gold/seed_gold.jsonl
  gold/full_gold.jsonl
  gold/annotation_template.csv
  rubrics/rubric.yaml
  scripts/README.md
  fixtures/
  results/
```

## Contract

- Eval type: `cv_classification`
- Target full gold size: `1000+ images`
- Seed cases: `3`
- Metrics: macro_f1, balanced_accuracy, auc, melanoma_sensitivity, specificity, calibration_ece

Replace placeholders with real fixtures/records before using any result as portfolio evidence.
