# PROVEDIt demonstration inputs

This subset contains one allelic ladder and three single-source GlobalFiler HID profiles. Each file is an unchanged binary copy. The original collection name is **PROVEDIt_1-Person Profiles_3500 15sec_GF29cycles**, and all four files come from **15sec/RD14-0003(072415CMG_15sec)**.

| File | Role | Donor ID | Nominal template |
| --- | --- | --- | --- |
| `A01_Ladder-GF_01.15sec.hid` | Allelic ladder | — | — |
| `B01_RD14-0003-01d2a-0.5GF-Q0.7_02.15sec.hid` | Single-source profile | 01 | 0.5000 ng |
| `B07_RD14-0003-02d2a-0.0625GF-Q0.8_02.15sec.hid` | Single-source profile | 02 | 0.0625 ng |
| `A04_RD14-0003-01d3c-0.0078GF-Q0.8_01.15sec.hid` | Single-source profile | 01 | 0.0078 ng |

Acquisition: ABI 3500, GlobalFiler, 29 PCR cycles, 15 s injection. Exact source-relative paths and file sizes are in [manifest.csv](manifest.csv). Total raw input size: **3,458,672 bytes**.

The subset was selected to exercise a ladder and three input amounts. It is small and deliberately unbalanced; it does not represent the full study population. Nominal amounts and donor labels follow the public source filenames.

## Run settings

Use project type **3 — hid/fsa Analyzer**; import this folder; choose kit `GlobalFiler_3500`, standard `ABI-LIZ-600-60-TO-460`, threshold **50 RFU**, and type `0-Uncertain`. Click **AI(P)** for the batch.

The example run produced three sample TXT tables, available in [observed-output](../observed-output). The ladder was displayed as **Mixture**, and the samples as **Single**. The ladder is a calibration profile and must not be counted as an additional donor mixture.

## Reference genotypes

[known-genotypes.tsv](known-genotypes.tsv) contains the 24 marker values for source donor IDs 1 and 2, transcribed programmatically from **PROVEDIt_RD14-0003 GF Known Genotypes.xlsx**, sheet **Sheet1**, rows with **Research ID = RD14-0003** and **Sample ID = 1 or 2**. The original workbook is not included.

The `source_genotype` field preserves the workbook text, including repeated alleles for homozygotes and `N/A` for absent Y markers. Comparisons with unique allele-call sets must account for these conventions, marker capitalization and expected absence. Observed software output is not the reference genotype.

## Attribution and terms

Alfonse LE, Garrett AD, Lun DS, Duffy KR, Grgicak CM. A large-scale dataset of single and mixed-source short tandem repeat profiles to inform human identification strategies: PROVEDIt. *Forensic Science International: Genetics*. 2018;32:62–70. [doi:10.1016/j.fsigen.2017.10.006](https://doi.org/10.1016/j.fsigen.2017.10.006).

[Original provider and downloads](https://lftdi.camden.rutgers.edu/provedit/files/), accessed 9 November 2026. The provider asks users to cite the paper above when reporting deductions from PROVEDIt. An explicit redistribution license was not found in the local source folder or on the inspected download page. The original data-provider terms apply; no new license is assigned by this repository.
