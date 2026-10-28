# CIP-B107 LAB-01 — AI-Assisted IP Evidence Identification

**Course:** CIP-B107 — AI for Forensics and Capstone Intelligence A  
**Case ID:** ICDFA-DFIR-AI-026  
**Student:** Mary Ekwughaonu  
**Registration:** c11.dfit2617295  
**Date:** 28 October 2026  

---

## Overview

This repository contains the laboratory deliverables for **LAB-01: AI-Assisted IP Evidence Identification**.

The investigation examined whether IP-like strings in a teaching dataset can be separated into IP-evidence candidates versus non-IP / version-like text using:

- Transparent rules (regex + strict IPv4 validation)
- A reproducible offline classifier (TF-IDF + Logistic Regression)

Work covers **Phases A–F** as required by the laboratory brief.

---

## Important notice

**Original evidence files are not included** in this repository (course policy).  
Integrity is documented via SHA-256 hashes and the evidence manifest only.

Legacy fine-tuning / upload / prediction scripts from the teaching package were **not executed** (obsolete API patterns / credentials).

---

## Repository structure
P-B107-LAB01-c11.dfit2617295_Mary_Ekwughaonu/
├── README.md
├── Hashes/                  # SHA-256 integrity records
├── Exports/                 # Manifest, predictions, metrics, model, plots
├── Findings/                # Consolidated findings summary
├── Report/                  # Phase A–F reports + full laboratory PDF
├── Notebooks/               # Reproducible Phase B–E Python scripts
├── Notes/                   # Complete command log
├── Screenshots/             # Supporting figures
├── Original/                # Empty (evidence not submitted)
└── Working/                 # Empty (working copy not submitted)

---

## Key results (holdout n = 46)

| Metric              | Value   |
|---------------------|---------|
| Accuracy            | 0.9783  |
| Precision           | 0.9714  |
| Recall              | 1.0000  |
| F1                  | 0.9855  |
| AUROC               | 0.9902  |
| AUPRC               | 0.9965  |
| Majority baseline   | 0.7391  |

**Outcomes:** TP = 34 · TN = 11 · FP = 1 · FN = 0  

Rule-based baseline accuracy ≈ 0.9565.

---

## Phase summary

| Phase | Focus |
|-------|--------|
| **A** | Evidence preservation, hashing, manifest, dataset profiling (229 rows; 183 train / 46 test) |
| **B** | Candidate extraction (285 rows); regex vs strict IPv4 vs source label |
| **C** | Offline TF-IDF + LogReg classifier + rule baseline; model and metrics saved |
| **D** | Historical fine-tuning log inspected only (no API re-run) |
| **E** | Actual-vs-predicted table, analyst review (≥7 records), high-accuracy counter-example |
| **F** | Forensic intelligence memorandum + executive briefing |

---

## Main deliverables

- `Report/CIP-B107_LAB01_Full_Report_c11.dfit2617295_Mary_Ekwughaonu.pdf` — full laboratory report  
- `Exports/evidence_manifest.csv` — chain-of-custody manifest  
- `Exports/candidate_review.csv` — Phase B candidate table  
- `Exports/predictions.csv` / `actual_vs_predicted_table.csv` — Phase C/E predictions  
- `Exports/analyst_review_8records.csv` — analyst review records  
- `Exports/tfidf_logreg_pipeline.joblib` — fitted offline model  
- `Exports/confusion_matrix_phaseC.png` / `phaseD_historical_metrics.png` — figures  
- `Findings/Lab01_Findings_Summary.txt` — consolidated findings  
- `Notes/complete_commands_Phases_A_to_E.txt` — command log  

---

## Operational conclusion

Rules and the offline classifier triage IP-like strings well on this teaching set.  
**Use only as analyst assistance.** Borderline or negative predictions that still contain dotted-decimal strings must be escalated for human review. Do not deploy as an autonomous discard filter.

---

## Author

Mary Ekwughaonu  
Registration: c11.dfit2617295  
CIP-B107 LAB-01 | October 2026
