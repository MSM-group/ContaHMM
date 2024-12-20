# Metadata README

This directory contains metadata tables associated with the sequences used in this study. Two key metadata files are provided:

---

## Metadata Files

### 1. `20241220_source_up_chemical_metadata_with_clusters.csv`
- **Description**: Metadata table for all sequences with assigned cluster numbers *prior to filtering*.  
- **Note**: The number of entries in this file exceeds the number of sequences in `20240927_biodeg_collection_via_up_deduplicated.faa`, as some sequences have multiple annotations, which are retained for completeness.

### 2. `20241220_all_metadata_filtered_final_names.csv`
- **Description**: Metadata table for sequences used in HMM generation *after filtering*.  
- **Filtering Criteria**:  
  - Removal of sub-sequences of longer sequences within the same cluster.  
  - Exclusion of eukaryotic sequences.  
  - Clusters with fewer than three members were discarded.

---

## Column Descriptions

| **Column Name**            | **Description**                                                                                                         |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------|
| `Fasta_id`                 | Sequence ID in the FASTA file (without full description).                                                               |
| `Cluster_num`              | Cluster index.                                                                                                         |
| `Fasta_header`             | Sequence ID in the FASTA file (with full description).                                                                 |
| `Source`                   | Source database of the sequence.                                                                                       |
| `Sequence`                 | Amino acid sequence.                                                                                                   |
| `up_entry`                 | UniProt entry.                                                                                                        |
| `Chemical_info`            | Chemical information from the source.                                                                                 |
| `Organism`                 | Source organism (UniProt metadata).                                                                                    |
| `Length`                   | Sequence length (UniProt metadata).                                                                                    |
| `Taxonomic lineage`        | Taxonomic classification (UniProt metadata).                                                                           |
| `KEGG`                     | KEGG annotations (UniProt metadata).                                                                                   |
| `eggNOG`                   | eggNOG database annotations (UniProt metadata).                                                                        |
| `EC number`                | Enzyme Commission number (UniProt metadata).                                                                           |
| `Function [CC]`            | Functional annotations (UniProt metadata).                                                                             |
| `Catalytic activity`       | Descriptions of catalytic activity (UniProt metadata).                                                                 |
| `Cofactor`                 | Cofactor details (UniProt metadata).                                                                                   |
| `Gene Ontology (GO)`       | Gene Ontology annotations (UniProt metadata).                                                                          |
| `rhea_id`                  | Rhea reaction IDs (UniProt metadata).                                                                                   |
| `rhea_derived_classes`     | Chemical classes assigned to Rhea reactions using Classyfire (detailed in the main README).                            |
| `taxon_label`              | Classification as eukaryote or prokaryote.                                                                             |
| `cluster_name`             | Manually assigned cluster and HMM name.                                                                                |
| `additional_chemical_info` | Supplementary chemical annotations from alternative sources.                                                           |
| `comments`                 | Notes on similar sequences from other sources.                                                                         |

---
