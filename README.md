# ContaHMM: A Resource for the search of Biotransformation-Related Bacterial Genes

## General Overview

We present a dataset and HMMs (Hidden Markov Models) for biotransformation-related bacterial genes, compiled from existing databases and enhanced by extensive metadata collection, manual curation, and HMM generation. This resource includes:


- **197 HMMs** of enzymes linked to specific contaminant biotransformations for identifying homologs.
- **Sequences and metadata** used for model generation, accompanied by a detailed metadata table.
- Comprehensive documentation of the sequential steps and methods used to create ContaHMM.

This collection aims to facilitate the annotation of biotransformation-related enzymes and expand the known examples in the field.

---

## Gene Collection

Biotransformation-related genes were sourced from:

- **Xenobiotics modules in KEGG**
- **HADEG** ([Rojas-Vargas et al., 2023](https://doi.org/10.1016/j.compbiolchem.2023.107966))
- **MiBPOP** ([Ngara et al., 2022](https://doi.org/10.1093/imeta/e45))
- **PlasticDB** ([Gambarini et al., 2022](https://doi.org/10.1093/database/baac036))
- **PMDB** ([Gan & Zhang, 2019](https://doi.org/10.1093/database/baz119))
- Experimentally validated genes from collaborators:
  - *M. Zimmermann’s lab (EMBL)*
  - *Dr. YaoChun Yu (K. Fenner’s lab, UZH/Eawag)*
- **Enzymatic defluorination collection** ([Wackett & Robinson, 2024](https://doi.org/10.1042/BCJ20200792))

---

## Metadata Collection

- Metadata was unified and merged from the combined databases.
- Sequences with UniProt IDs were enriched with fields such as `organism` and `EC number`.
- **Chemical and reaction data** were enhanced using the Rhea database, cross-referenced with UniProt.
  - Rhea identifiers were linked to reaction descriptions with CheBI identifiers where available.
- Chemical transformations were classified using **ClassyFire** ([Djoumbou Feunang et al., 2016](https://doi.org/10.1186/s13321-016-0174-y)) and SMILES representations.
  - Annotation at the ‘subclass’ level was used, but these classifications should be interpreted cautiously.

---

## Clustering and Alignment

Sequence clustering and alignment were key preliminary steps for HMM generation:

### Clustering
- Tool: **Markov Clustering (MCL)** ([Van Dongen, 2008](https://doi.org/10.1137/040608635))
- Pairwise distance matrix generated using **BLAST** ([Ye et al., 2006](https://doi.org/10.1093/nar/gkl383))
- Protocol: [MCL Clustering Protocol](https://micans.org/mcl/man/clmprotocols.html)

#### Clustering Results
- **569 clusters** and **198 singletons** obtained.
- Clusters with at least three members were used for HMM generation (197 in total).

### Alignment
- Tool: **ClustalW** ([Thompson et al., 2002](https://doi.org/10.1002/0471250953.bi0203s00))

---

## Cluster and HMM Naming

Clusters and corresponding HMMs were manually reviewed and named based on representative chemical classes:

- Clusters containing defluorinating enzymes were labeled as “defluorinating,” even though this is not a strict chemical class.
- Each cluster name includes a representative UniProt ID to facilitate quick reference and searches.

HMMs were generated from multisequence alignments using **HMMER** ([hmmer.org](http://hmmer.org)).

---


See in the subdirectories additional detailed information about the methods, algorithms, and data used. We invite users to leverage this resource for advancing the study and annotation of biotransformation-related enzymes.

---

## References

1. Rojas-Vargas, J., Castelán-Sánchez, H. G., & Pardo-López, L. (2023). [HADEG: A curated hydrocarbon aerobic degradation enzymes and genes database.](https://doi.org/10.1016/j.compbiolchem.2023.107966) *Comput Biol Chem, 107*, 107966.
2. Ngara, T. R., Zeng, P., & Zhang, H. (2022). [mibPOPdb: An online database for microbial biodegradation of persistent organic pollutants.](https://doi.org/10.1093/imeta/e45) *iMeta, 1*, e45.
3. Gambarini, V., et al. (2022). [PlasticDB: a database of microorganisms and proteins linked to plastic biodegradation.](https://doi.org/10.1093/database/baac036) *Database (Oxford), 2022*.
4. Gan, Z., & Zhang, H. (2019). [PMBD: A Comprehensive Plastics Microbial Biodegradation Database.](https://doi.org/10.1093/database/baz119) *Database (Oxford), 2019*.
5. Wackett, L. P., & Robinson, S. L. (2024). [A prescription for engineering PFAS biodegradation.](https://doi.org/10.1042/BCJ20200792) *Biochem J, 481*, 1757–1770.
6. Djoumbou Feunang, Y., et al. (2016). [ClassyFire: automated chemical classification with a comprehensive, computable taxonomy.](https://doi.org/10.1186/s13321-016-0174-y) *J Cheminform, 8*, 61.
7. Van Dongen, S. (2008). [Graph clustering via a discrete uncoupling process.](https://doi.org/10.1137/040608635) *SIAM J. Matrix Anal. Appl, 30*, 121–141.
8. Ye, J., McGinnis, S., & Madden, T. L. (2006). [BLAST: improvements for better sequence analysis.](https://doi.org/10.1093/nar/gkl383) *Nucleic Acids Res, 34*, W6–9.
9. Thompson, J. D., Gibson, T. J., & Higgins, D. G. (2002). [Multiple sequence alignment using ClustalW and ClustalX.](https://doi.org/10.1002/0471250953.bi0203s00) *Curr Protoc Bioinformatics, Chapter 2, Unit 2.3*.

