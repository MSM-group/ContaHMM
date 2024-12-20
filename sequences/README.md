# Sequences README

This repository contains biotransformation-related gene sequences compiled from various sources. Below is an overview of the sources and the data processing steps.

---

## Gene Sources

1. **Xenobiotics Modules in KEGG**
2. **HADEG**
3. **MiBPOP**
4. **PlasticDB (2019 version)**
5. **PMDB**
6. **Experimentally Validated Genes from Collaborators**:
   - M. Zimmermann’s lab (EMBL)
   - Dr. YaoChun Yu (K. Fenner’s lab, UZH/Eawag)
7. **Enzymatic Defluorination Genes** from Wackett & Robinson (2024)

---

## Sequence and Metadata Extraction

- The primary source for sequence and metadata extraction was **UniProt**.

### Data Integration Process

- **Databases 2–5**: UniProt IDs were directly linked to the respective databases.
- **Databases 6–7**: Sequences were provided by collaborators.
- **Database 1 (KEGG)**: KOs linked to Xenobiotics KEGG modules were used to retrieve UniProt IDs.

---

## Processed Sequence Collection

The file `20240927_biodeg_collection_via_up_deduplicated.faa` contains **3,102 unique amino acid sequences** compiled from the sources listed above.

### Deduplication

- Deduplication was performed using the `seqkit rmdup` function.

---
