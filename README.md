# Module I: Whole Genome Sequencing (WGS) Analysis
## Unix Essentials for Genomics Data Processing

Welcome to **Module I: WGS Analysis**. This repository contains hands-on tutorials and practice datasets designed to teach foundational Unix command-line skills and high-throughput sequencing data processing.

---

## 📖 How to Use This Tutorial

To get the most out of this module:
1. **Read the Tutorials in Sequence:** Start with Chapter 2F to master fundamental Unix operations, then proceed to Chapter 3A to work with real genomics data.
2. **Execute Every Command in Your Terminal:** Do not just read through—open your terminal, type or paste each command, observe the terminal output, and inspect the files.
3. **Explore and Experiment:** Check file outputs with `head`, `less`, and `wc` as you pipe commands together. Try tweaking parameters (e.g., `-n`, `-k`, `-w`) to see how the results change.

---

## 🗂️ Tutorial Chapters

### 1. [Chapter 2F: How to Work on Unix Systems (Hands-on Session)](./2F.-Day-1:-How-to-Work-on-Unix-System-(Hands-on-Session).md)
* **Objective:** Learn basic navigation, directory hierarchies, file permissions, creation, and stream manipulation.
* **Topics Covered:**
  * Directory navigation: `pwd`, `cd`, `ls -lah`
  * Creating files and folders: `mkdir -p`, `nano`
  * Inspecting content: `cat`, `less`, `head`, `tail`
  * File management: `cp`, `mv`, `rm`
  * Standard streams & redirection: `stdin`, `stdout` (`>`), append (`>>`), and `stderr` (`2>`)
  * Compression & archiving: `gzip`, `tar -czvf`, `zip`, and `unzip`

### 2. [Chapter 3A: Unix Essentials for Genomics Data Processing (Hands-on Session)](./3A.-Day-2:-Unix-essential-for-genomics-data-processing-and-analysis-(Hands-on-Session).md)
* **Objective:** Process, filter, and extract biological metrics from raw sequencing reads (FASTQ) and reference sequences (FASTA).
* **Topics Covered:**
  * File integrity verification: `md5sum` / `md5`, and format validation with `file`
  * FASTQ 4-line architecture and read counting: `zcat` / `wc -l` and `grep -c "^@ERR"`
  * Multi-column text processing:
    * `cut`: Delimited field and character extraction
    * `paste`: Merging tables and the `paste - - - -` FASTQ 4-line reshaping idiom
    * `wc`: Line, word, character, and max line length counting
    * `grep`: Pattern searching, invert match (`-v`), and context lines (`-A`, `-B`)
    * `sort`: Alphabetical, numerical (`-n`), and column-based (`-k`) sorting
    * `uniq`: Deduplication and frequency counting (`-c`, `-d`, `-u`)
    * `fold`: Sequence wrapping and base-by-base breakdown (`fold -w 1`)
    * `sed`: Stream editing, pattern substitution, and range extraction
  * Genomics Math: Automating base composition (A/T/G/C counts), GC content (%), and primer melting temperature ($T_m$) using `bc`.
  * Hands-on Assignment: FASTQ-to-FASTA conversion, FASTA splitting, multi-line formatting, read subsampling, gene extraction, and non-redundant deduplication.

---

## 🚀 Getting Started & Data Setup

All demo datasets required for the exercises in Chapter 3A are bundled in `Day2.zip`.

Open your terminal and run:

```bash
# 1. Clone this repository (if not already local)
git clone https://github.com/bioinfokushwaha/Module-I-WGS-Analysis.git
cd Module-I-WGS-Analysis

# 2. Unpack the practice datasets
unzip Day2.zip

# 3. Enter the practice data directory
cd Day2

# 4. Verify your practice files
ls -lh
```

### 📁 Included Practice Datasets:
* **`Test.fq.gz` / `Test.fq`:** 10 real Illumina paired-end sequencing reads for quality inspection, line counting, and base composition analysis.
* **`Test.fa`:** Multi-sequence FASTA file for sequence counting and pattern matching with `grep`.
* **`id.txt`:** Transcriptome sample identifiers (`TCONS_...`) for `cut` and `paste` field extraction.
* **`family.txt`:** Peptidase classification annotations matching `id.txt`.
* **`Features.txt`:** Genomic feature types (`promoter`, `exon`, `intron`, `mRNA`, `protein`) for sorting.
* **`Exon.txt`:** Two-column feature and coordinate table with duplicate entries for testing numeric sort and deduplication.

---

## 💡 Recommended Learning Workflow

```text
Clone Repo / Open Terminal
        │
        ▼
Read Chapter 2F ──► Practice navigation, file management, and I/O redirection
        │
        ▼
Unzip Day2.zip  ──► cd Day2
        │
        ▼
Read Chapter 3A ──► Run genomics pipelines (FASTQ counting, cut/paste/grep/sort/sed)
        │
        ▼
Solve Assignment 1 Tasks ──► Verify solutions against the guide
```
