# IFC-Based Facility Management Knowledge Graph QA Benchmark Dataset (Text-to-Cypher)

## Overview

This repository contains the evaluation benchmark and training data developed for the research study:
> **"Natural Language Querying of IFC-Based Facility Management Knowledge Graphs: A Comparative Evaluation of LLM Architectures"**


The dataset is designed to support the **systematic analysis** of Large Language Model (LLM) performance in converting natural language questions into graph database queries (Text-to-Cypher) in the context of Facility Management.

## Purpose & Utility
This dataset was created to address the lack of standardized evaluation resources for IFC-based FM knowledge graphs. It serves two primary functions:
1.  **Fine-Tuning:** It provides high-quality, curated examples suitable for **fine-tuning** LLMs to understand Industry Foundation Classes (IFC 4.3) schema constraints and Cypher syntax.
2.  **Benchmarking:** It acts as a test bed to evaluate the semantic reliability of different architectures.
---

## Dataset Description

The dataset consists of **500 manually curated Question–Answer (QA) pairs** focused on Facility Management (FM) work orders. Each QA pair maps a natural language question to an executable **Cypher** query that operates over an **IFC 4.3–compliant knowledge graph**.

The questions reflect realistic operational scenarios commonly encountered in FM contexts, including:

- Maintenance and corrective tasks  
- Cost and labor breakdowns  
- Temporal attributes and scheduling  
- Spatial hierarchy and topology (buildings, storeys, spaces)  

---

## Data Fields

Each record in the dataset contains the following fields:

- **`unique_id`**  
  Unique identifier for the query instance.

- **`semantic_intent_id`**  
  Identifier used to group questions with the same semantic intent. This field supports controlled data splitting and prevents leakage across train, validation, and test sets.

- **`question_text`**  
  The natural language query, provided in anonymized form.

- **`reference_answer`**  
  The ground-truth Cypher query corresponding to the question, anonymized using placeholders.

- **`data_split`**  
  Dataset partition assignment. Possible values: `train`, `validation`, `test`.

- **`difficulty_level`**  
  Structural complexity of the query. Possible values:
  - Trivial  
  - Simple  
  - Moderate  
  - Complex  
  - Extremely Complex  

---

## Data Privacy and Reproducibility

To preserve privacy and support reproducibility across institutions, all sensitive identifiers and organization-specific values have been replaced with standardized placeholders in both the questions and the Cypher queries.

Examples include:
 
- `<PRIORITY_LABEL>`  
- `<WORK_ORDER_ID>`  
- `<PERSON_ID>`

Users may substitute these placeholders with values from their own datasets to execute the queries in their local environments.

---

## File Information

- **Format:** JSON Lines (`.jsonl`)  
- **Total Records:** 500  
- **Query Language:** Cypher (Neo4j)  
- **Domain:** Facility Management Work Orders and IFC 4.3 Knowledge Graphs  


---


## Citation

If you use this dataset in academic work, please cite the associated paper accordingly.
