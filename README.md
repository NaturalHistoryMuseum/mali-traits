# Trait Extraction (& Knowledge Integration) Pipeline

This repository contains a set of Jupyter notebooks that together form a modular pipeline for scraping botanical descriptions, extracting phenotypic traits using LLMs, linking traits to standardised community ontologies, and experimenting with assembling a structured trait knowledge base.  
Each notebook focuses on a specific task, and they can be combined into a full end-to-end workflow.

---

## Overview of Notebooks

### **`notebooks/combined.ipynb`**
A small **test case notebook** demonstrating how the core components of the pipeline work together - for quick debugging and sanity checks without processing the full dataset.

---

### **`notebooks/wfo_scraper.ipynb`**
A configurable web-scraping workflow that:
- automatically retrieves **taxon descriptions** in all available languages,
- uses a user-provided list of `scientific_name` values (the list can be updated as needed),
- outputs structured text suitable for downstream trait extraction.

This notebook performs the **data ingestion** step.

---

### **`notebooks/llm_pipeline.ipynb`**
A multilingual LLM-based pipeline for **trait extraction**, including:
- extraction in **English (EN), French (FR), German (DE), Portuguese (PT)**,
- deduplication of extracted traits,
- standardisation into a consistent **trait schema**.

This notebook is the core **trait extraction engine**.

---

### **`notebooks/test_ontogpt.ipynb`**
Experimental workflows to map extracted traits to community ontologies using:
- **FLOPO** (Flora Phenotype Ontology),
- **PATO** (Phenotype And Trait Ontology),
- **FAISS** vector search,
- transformer-based semantic matching.

This notebook provides the **ontology grounding** step.

---

### **`notebooks/trait_knowledge_base_builder.ipynb`**
A prototype workflow for assembling ontology-aligned traits into a **knowledge graph**.

This notebook experiments with building the final **trait knowledge base**. (In progress)

---

## Recommended Workflow

1. **Scrape descriptions** → `wfo_scraper.ipynb`  
2. **Extract traits** → `llm_pipeline.ipynb`  
3. **Link traits to ontologies** → `test_ontogpt.ipynb`  
4. **Build a knowledge graph** → `trait_knowledge_base_builder.ipynb`  
5. **Test or debug small examples** → `combined.ipynb`

---

## Notes

- All notebooks are modular and can be run independently.  
- The pipeline supports **multilingual inputs**.  
- Ontology-linked outputs are designed for integration into broader biodiversity knowledge graph projects and future open data linkages.

