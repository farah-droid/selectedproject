# DSAI4201 — Group 6: LLM Reasoning Failures

**Course:** Selected Topics for AI — DSAI4201  
**Professor:** Uzair Ahmad  
**Group:** 6 | Seminar 2  
**Due Date:** April 1, 2025  

---

## Group Members

| Name | Student ID | Sections |
|------|-----------|---------|
| Farah Darweesh | 60104565 | 4.1 — Reversal Curse, 4.2 — Compositional Reasoning |
| Hind Benkhaled | 60105179 | 4.3 — Counting, 4.4 — Basic Arithmetic |

---

## What This Repo Contains

This repository documents our testing of 4 fundamental LLM reasoning failures identified in the survey paper:

> **"Large Language Model Reasoning Failures"** — Song, Han & Goodman (2026) · arXiv:2602.06176

We designed 20 questions (10 per member) and tested them on 4 LLMs:
- **ChatGPT** (GPT-5.3)
- **Gemini 3**
- **DeepSeek** (Instruct)
- **Claude**

Each question was tested in a **fresh chat** to prevent context contamination.

---

## Repo Structure

```
DSAI4201_Group6/
│
├── README.md                          ← You are here
│
├── Farah_Section4.1_4.2/             ← Farah's work
│   ├── questions.docx                   ← 10 test questions
│   ├── Farah_Report_Sections4.1_4.2.docx
│   ├── Farah_Results_Sections4.1_4.2.xlsx
│   └── responses/
│       ├──responses.docx
│
└── Hind_Section4.3_4.4/              ← Hind's work
    ├── questions.docx                  ← 10 test questions
    ├── Hind_Report_Sections4.3_4.4.docx
    ├── Hind_Results_Sections4.3_4.4.xlsx
    ├── screenshots/
    │   ├── chatgpt_loading_dot_rhythm.png
    │   ├── chatgpt_instruments_calculator.png
    │   └── chatgpt_stuck_lastdigit.png
    └── responses/
        ├── responses.docx
```

---

## Key Findings

| Section | Failure Type | ChatGPT | Gemini 3 | DeepSeek | Claude |
|---------|-------------|---------|---------|---------|--------|
| 4.1 | Reversal Curse | 100% | 100% | 100% | 100% |
| 4.2 | Compositional Reasoning | 80%* | 80%* | 80%* | 80%* |
| 4.3 | Counting | 60% | 100% | 100% | 80% |
| 4.4 | Basic Arithmetic | 80% | 100% | 100% | 80% |
| **Overall** | — | **80%** | **95%** | **95%** | **85%** |

*Q9 was a flawed question with no valid answer — all models hallucinated a confident but incorrect response.

### Notable Behavioral Finding
ChatGPT used its built-in **"ChatGPT Instruments" calculator** for arithmetic questions and its **code interpreter** for counting tasks — rather than answering natively. This is direct behavioral evidence that the architectural failures documented in the original papers still exist in modern LLMs, even when surface-level accuracy appears high.

---

## Papers Referenced

- Berglund et al. (2023) — The Reversal Curse · arXiv:2309.12288 · ICLR 2024
- Dziri et al. (2023) — Faith and Fate: Limits of Transformers on Compositionality · arXiv:2305.18654 · NeurIPS 2023
- Xu & Ma (2024) — Counting Failures in LLMs · §4.3
- Yuan et al. (2023) — Arithmetic Failures in LLMs · arXiv:2304.02015
- Song, Han & Goodman (2026) — LLM Reasoning Failures Survey · arXiv:2602.06176
