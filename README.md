# 🏥 Medical Records Data Validator

A Python script that validates structured medical record datasets against predefined schema rules, data types, and formatting constraints using regular expressions.

---

## 📌 Overview

When processing medical datasets, maintaining clean, valid data is critical. This script provides automated validation for lists of patient record dictionaries, flagging structural errors, missing keys, and invalid field values (such as malformed patient IDs, out-of-range ages, or non-list medication fields).

---

## ✨ Features

* **Structure Validation:** Ensures input data is a valid sequence (`list` or `tuple`) containing dictionaries.
* **Schema Enforcement:** Verifies that every record contains the exact set of required keys.
* **Type & Format Checking:**
  * **Patient ID:** Case-insensitive match for `P` followed by digits (e.g., `P1001`, `p1002`).
  * **Age:** Must be an integer $\ge 18$.
  * **Gender:** Case-insensitive check for `'male'` or `'female'`.
  * **Diagnosis:** String value or `None`.
  * **Medications:** Must be a list of strings.
  * **Last Visit ID:** Case-insensitive match for `V` followed by digits (e.g., `V2301`, `v2302`).
* **Detailed Error Logging:** Reports the exact index and invalid key-value pair for fast debugging.

---

## 🛠️ Code Structure

```plaintext
├── medical_records         # Sample dataset containing patient records
├── find_invalid_records()  # Evaluates field-level constraints on a single record
└── validate()              # Iterates through dataset and reports errors
