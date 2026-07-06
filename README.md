# WS/DGAT Biosynthetic Potential in Marine and Terrestrial Environments

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)
![scipy](https://img.shields.io/badge/scipy-8CAAE6?style=flat&logo=scipy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-E97627?style=flat&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/status-complete-brightgreen?style=flat)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat)

## The Problem

The oleochemical industry (biofuels, lubricants, bioplastics) needs new biocatalysts to replace petroleum-derived feedstocks. Most of that enzymatic diversity sits in bacteria that have never been grown in a lab — the classic bottleneck for enzyme bioprospecting.

**This project bypasses that bottleneck with computational metagenomics: mining large public sequence datasets — marine and terrestrial metagenomes and 18,000+ bacterial genomes — for a target biocatalyst (WS/DGAT enzyme family) at a scale no wet-lab screen could match.**

---

## Biological & Business Impact

- Identified **WS/DGAT enzyme homologs** (Pfam domain PF03007) across marine and terrestrial metagenomes and thousands of bacterial reference genomes
- Quantified **relative abundance** of biosynthetic potential normalized to 12 single-copy ribosomal marker genes — enabling cross-environment comparability
- Characterized **taxonomic diversity** of WS/DGAT-carrying microorganisms across environments
- Analyzed **ecological partitioning** between free-living and particle-attached microbial fractions (Malaspina expedition)
- Mapped **global distribution** of WS/DGAT biosynthetic potential across marine and terrestrial environments

---

## Repository Structure

```
wsdgat-biosynthetic-potential/
├── data/
│   ├── Metagenomes_Data_Table.xlsx
│   ├── counts_pf03007_and_ribosomal_pfams.xlsx
│   ├── taxonomic_assignment_13_metagenomes_repo1.xlsx
│   ├── local_metagenomes_coordinates_repo1.csv
│   ├── Actinob_Tree_curated.nwk
│   ├── marine_metagenomes_gene_counts_repo1.csv
│   ├── marine_metagenomes_metadata_repo1.csv
│   ├── global_marine_metagenomes_summary_table.csv
│   ├── terrestrial_metagenomes_gene_counts_repo1.csv
│   ├── terrestrial_metagenomes_metadata_repo1.csv
│   ├── terrestrial_metagenomes_summary_table.csv
│   ├── malaspina_gene_counts_repo1.csv
│   ├── malaspina_metadata_repo1.csv
│   ├── malaspina_summary_table.csv
│   ├── bacterial_genomes_pf03007_repo1.csv
│   ├── bacterial_genomes_phylum_summary_repo1.csv
│   └── bacterial_genomes_class_summary_repo1.csv
├── notebooks/
│   ├── 01_local_metagenomes_abundance.ipynb        # Relative abundance — 13 local metagenomes
│   ├── 02_taxonomic_classification.ipynb           # Taxonomic distribution of WS/DGAT sequences
│   ├── 03_phylogenetic_analysis.ipynb              # Phylogenetic tree of WS/DGAT homologs
│   ├── 04_global_marine_metagenomes.ipynb          # Global survey — 101 marine metagenomes + map
│   ├── 05_terrestrial_metagenomes.ipynb            # Global survey — 219 terrestrial metagenomes
│   ├── 06_malaspina_freeliving_vs_particle.ipynb   # Free-living vs particle-attached fractions
│   └── 07_bacterial_genomes_survey.ipynb           # PF03007 distribution across bacterial genomes
├── figures/
│   ├── fig0_sampling_sites_map.png
│   ├── fig1_relative_abundance.png
│   ├── fig2_spearman_correlation.png
│   ├── fig1_taxonomic_composition.png
│   ├── fig2_regional_comparison.png
│   ├── fig1_actinomycetota_tree.png
│   ├── fig2_composition_summary.png
│   ├── figure1_global_marine_relative_abundance_ranked.png
│   ├── figure2_global_marine_metagenomes_map.html
│   ├── figure3_terrestrial_relative_abundance_ranked.png
│   ├── figure4_marine_vs_terrestrial_comparison.png
│   ├── figure5_malaspina_paired_comparison.png
│   ├── figure6_bacterial_genomes_pf03007_by_phylum.png
│   └── figure7_bacterial_genomes_pf03007_by_class.png
└── README.md
```

---

## Notebooks

| # | Notebook | Status | Description |
|---|---|---|---|
| 01 | `01_local_metagenomes_abundance.ipynb` | ✅ Complete | Relative abundance of WS/DGAT homologs across 13 Subantarctic and Antarctic metagenomes; sampling-site satellite map; Mann-Whitney U and Spearman correlation |
| 02 | `02_taxonomic_classification.ipynb` | ✅ Complete | Taxonomic assignment of WS/DGAT sequences via BLASTp + MEGAN6 weighted LCA; regional comparison (Subantarctic vs Antarctic) of indicator taxa |
| 03 | `03_phylogenetic_analysis.ipynb` | ✅ Complete | ML tree (125 seqs, Actinomycetota/OR07) — origin classification, clade dispersion, nearest-relative analysis |
| 04 | `04_global_marine_metagenomes.ipynb` | ✅ Complete | Survey of 101 marine metagenomes from IMG/M; QC + duplicate-exclusion logic, sequencing-depth correction check, geographic distribution map, ranked abundance, GOLD Study clustering |
| 05 | `05_terrestrial_metagenomes.ipynb` | ✅ Complete | Survey of 227 terrestrial metagenomes from IMG/M (210 pass QC); per-project breakdown; Mann-Whitney comparison vs. marine survey (Notebook 04) |
| 06 | `06_malaspina_freeliving_vs_particle.ipynb` | ✅ Complete | Paired comparison (Wilcoxon signed-rank) of WS/DGAT abundance between free-living and particle-attached fractions across 25 fully-paired Malaspina deep-ocean stations (50 metagenomes) |
| 07 | `07_bacterial_genomes_survey.ipynb` | ✅ Complete | PF03007 presence and copy number across 18,392 bacterial genomes (IMG/M), grouped by phylum and class |

---

## Dataset & Data Provenance

### Local metagenomes (Notebooks 01–03)

Subtidal sediment metagenomes are publicly available at the **Integrated Microbial Genomes & Microbiomes (IMG/M)** system (https://img.jgi.doe.gov/) under study name *"Marine microbial communities from chronically polluted sediments"*:

| Metagenome | Region | Site | Matrix | IMG/M ID |
|---|---|---|---|---|
| ARG01 | Subantarctic | MC | Subtidal sediments | 3300000125 |
| ARG02 | Subantarctic | MC | Subtidal sediments | 3300000131 |
| ARG03 | Subantarctic | MC | Subtidal sediments | 3300000121 |
| ARG04 | Subantarctic | OR | Subtidal sediments | 3300000122 |
| ARG05 | Subantarctic | OR | Subtidal sediments | 3300000242 |
| ARG06 | Subantarctic | OR | Subtidal sediments | 3300000118 |
| ANT01 | Antarctic | S1 | Subtidal sediments | 3300000119 |
| ANT02 | Antarctic | S1 | Subtidal sediments | 3300000136 |
| ANT03 | Antarctic | S1 | Subtidal sediments | 3300000135 |
| ANT04 | Antarctic | S1 | Subtidal sediments | 3300000129 |
| ANT05 | Antarctic | S1 | Subtidal sediments | 3300000132 |
| ANT06 | Antarctic | S1 | Subtidal sediments | 3300000123 |
| OR07 | Subantarctic | OR | Intertidal sediments | — (see note) |

> **OR07:** in-house metagenomic library from a chronically hydrocarbon-contaminated intertidal site (Bahía Ushuaia, Argentina). Raw sequence data are not publicly available. WS/DGAT homolog sequences identified from this library were deposited in GenBank under accession numbers **OP731433–OP731569**.

### Where the counts come from

Gene counts were obtained by searching each metagenome for Pfam domain hits via **IMG/M**:

- **PF03007** (WS/DGAT domain): identifies putative neutral lipid biosynthesis genes
- **12 single-copy ribosomal protein domains** (PF00189, PF00252, PF00453, PF00542, PF00831, PF00886, PF01016, PF01196, PF01245, PF01250, PF01281, PF01649): used as reference markers to normalize for differences in metagenome size and sequencing depth

For assembled metagenomes, estimated abundances are corrected by scaffold read depth (as reported by IMG/M). **Relative abundance** is computed as the mean of 12 ratios (WS/DGAT estimated count / ribosomal marker estimated count), one per marker gene.

---

## Methods Summary

- **Gene identification:** Pfam domain search (PF03007 + 12 ribosomal markers) via IMG/M
- **Taxonomy:** BLASTp (top 100 hits, nr database) + weighted LCA via MEGAN6
- **Phylogenetics:** Multiple sequence alignment (Jalview) + maximum likelihood tree (MEGA-X); visualized in Python
- **Genome-scale survey:** function-based search (PF03007) across all bacterial genomes in IMG/M; presence, copy number, and taxonomic distribution at phylum/class level
- **Statistics:** Mann-Whitney U test; Wilcoxon signed-rank test (paired designs); Spearman correlation
- **Tools:** IMG/M, MEGAN6, MEGA-X, Jalview, Python (pandas, scipy, matplotlib, Biopython, geopandas)

---

## Related Publication

**Galván et al. (2023).** High potential for the biosynthesis of neutral lipid storage compounds in chronically-polluted subantarctic sediments. *PLOS ONE.*
https://doi.org/10.1371/journal.pone.0288509

---

## How to Run

```bash
git clone https://github.com/virginiagalvan/wsdgat-biosynthetic-potential.git
cd wsdgat-biosynthetic-potential
pip install pandas scipy matplotlib openpyxl biopython
jupyter notebook notebooks/01_local_metagenomes_abundance.ipynb
```

**Google Colab:** open any notebook in Colab and upload the required files from `data/` when prompted.

---

## Author

**Virginia Galván, PhD** · Genomic Data Scientist | Bioinformatics
