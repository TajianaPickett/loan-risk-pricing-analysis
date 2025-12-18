# Loan Risk & Pricing Analysis

## Overview
This project analyzes a large consumer loan portfolio using **Apache Spark (PySpark)** to identify **risk concentration**, **pricing misalignment**, and the impact of **policy and pricing decisions** on expected losses. The focus is on **portfolio-level risk management**, not black-box prediction.

---

## Dataset
- **255,347 loans**
- **$32.6B total exposure**
- **Key variables:** credit score, DTI, income, employment status, loan purpose, co-signer, interest rate, default outcome

---

## Methodology
- Segment borrowers by **Credit Score × DTI** bands
- Compute segment-level **default rates**, **exposure**, and **expected loss proxies**
- Identify **underpriced segments** (above-average default, below-average interest rate)
- Simulate alternative **approval policies** and **targeted pricing adjustments**

---

## Key Findings
- **Overall portfolio default rate:** 11.6%
- Borrowers with **credit score <600 and DTI ≥0.35** account for the **largest expected loss**, with default rates up to **12.9%** while paying **below-average interest rates**
- Loans **without co-signers** show a **25% higher default rate** than comparable loans with co-signers
- Requiring **Credit Score ≥660 and DTI ≤0.40** reduces expected losses by **~$3.38B**, but cuts approvals to **13%**
- Requiring co-signers for borrowers with **credit score <640** preserves a **69% approval rate** while reducing expected losses by **~$1.38B**
- A **targeted 1% interest rate increase** applied only to underpriced segments improves pricing alignment across **~$13.9B in exposure** without reducing approvals

---

## Tools
- **PySpark**
- **Spark SQL**

---

## Takeaway
Targeted pricing and moderate policy controls can reduce portfolio risk by **billions of dollars** without materially shrinking loan approvals, highlighting the value of **data-driven credit risk management at scale**.
