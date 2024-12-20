# HMM README
In this directory you will find a single file with all the generated hmms 20241216_conta.hmm, and a subdirectory HMMs/single_hmm_files with the HMMs in separate files.

Below you can find the steps involved in the generation of Hidden Markov Models (HMMs), including prerequisite calculations, clustering, alignment, and HMM generation.

---

## Prior Steps to HMM Generation

1. **All-vs-All Similarity Matrix Calculation**
   - Tool: BLAST  

2. **Clustering**
   - Tool: Markov Cluster Algorithm (MCL)

3. **Multiple Sequence Alignment**
   - Tool: Clustal Omega

### Installation and Usage
- Information about MCL installation and usage can be found here:  
  [MCL GitHub Repository](https://github.com/micans/mcl?tab=readme-ov-file)

### HMM Generation Tool
- HMMs were generated using **HMMER**. For more information, visit [HMMER](http://hmmer.org).

---

## Commands

### 1. BLAST Commands

#### Create a BLAST Database
```bash
makeblastdb -in "$gene_db_path" -dbtype prot -out "$output_db_path"
```

#### Perform All-vs-All Similarity Search
```bash
blastp -query "$gene_db_path" -db "$output_db_path" -out "$results_path" \
       -outfmt "6 qseqid qlen saccver ssciname pident qcovs length evalue bitscore" \
       -num_threads 64 -evalue 1e-2 -word_size 2 -seg no
```

---

### 2. MCL Commands

For clustering, follow the instructions provided in the **"Clustering similarity graphs encoded in BLAST results"** section of the [MCL Manual](https://micans.org/mcl/man/clmprotocols.html).

#### Prepare BLAST Results for MCL
```bash
cut -f 1,3,8 blast_similarity_results.txt > blast_similarity.abc
```

#### Load and Process Similarity Graph
```bash
mcxload -abc blast_similarity.abc --stream-mirror --stream-neg-log10 \
        -stream-tf 'ceil(200)' -o blast_similarity.mci -write-tab blast_similarity.tab
```

#### Perform Clustering
```bash
mcl blast_similarity.mci -I 2
```

#### Dump Cluster Results
```bash
mcxdump -icl out.blast_similarity.I2 -tabr blast_similarity.tab \
        -o dump.blast_similarity.mci.I2
```

---

### 3. Alignment Command

```bash
clustalo -i input_fasta_file -o output_alignment --force
```

---

### 4. HMM Generation

#### Generate HMMs Using HMMER
```bash
mmbuild hmm_name alignment_fasta_file
```

---
