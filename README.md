# ACE — Analyzer of Capillary Electrophoresis

ACE is an intelligent, high-throughput signal processing and probabilistic STR genotyping platform for capillary electrophoresis (CE). It automates the complete workflow from raw **HID/FSA** files through peak detection, internal size-standard sizing, allelic ladder fitting, allele designation, and probabilistic peak curation in an interactive graphical environment.

This repository provides **ACE v1.0** for Windows, an illustrated user guide, and a small demonstration dataset from the public PROVEDIt collection. Launch the application with `ACE.cmd`.

![ACE Multichannel Electropherogram Viewer](docs/images/profile.png)

---

## Key Features

- **End-to-End Automated Genotyping**: Directly parses raw ABI 3500 (`.hid`) and ABI 3130 (`.fsa`) capillary electrophoresis files without third-party converters.

- **Robust Sizing & Ladder Fitting**: Supports standard internal size standards (e.g., ABI-LIZ-600, ABI-LIZ-500) and commercial STR amplification kits (e.g., GlobalFiler, Identifiler).

- **Probabilistic Artifact Curation**: Automated discrimination and removal of PCR stutter (−1 and +1 slippage), spectral pull-up, dye blobs, and voltage spikes, while preserving true alleles and supported stutter for downstream probabilistic genotyping (STRmix™, EuroForMix, TrueAllele®).

- **Interactive Multi-Dye Visualization**: Full 5-dye and 6-dye electropherogram viewer with allelic bin overlays, manual peak curation dialogs, and instant zoom/pan controls.

- **Auditable Quality Scoring**: Sample-level and peak-level quality indicators with complete traceability.

---

## Download & Installation

### Windows Portable Package

1. Open the repository's **Releases** page and download **`ACE-v1.0-windows.zip`** (~305 MiB).
2. Extract the archive to any local, writable directory (e.g., `D:\test\ACE`).
3. Open the **ACE** folder inside the extracted archive and double-click **`ACE.cmd`**.

> [!NOTE]
> The portable package includes a Java runtime (Zulu JRE 22); no separate Java installation or environment variable configuration is required. The launcher sets a 4 GiB Java heap limit and creates the local results directory automatically. Software authorization is required.

### ACE v1.0 loading screen

The loading screen displays the ACE name and version.

![ACE v1.0 loading screen](docs/images/splash.png)

---

## PROVEDIt Example Walkthrough

The repository includes a small demonstration subset from the public **PROVEDIt** collection in [examples/provedit](examples/provedit). It contains one GlobalFiler allelic ladder and three single-source HID profiles (3.30 MiB total; inputs: **0.5000 ng**, **0.0625 ng**, and **0.0078 ng**).

### Step 1: Start ACE & Create Project

Launch ACE to access the main welcome screen. Click **Create a new project**.

![Welcome Home Screen](docs/images/home.png)

In the project creation dialog:

- **Project Path**: Choose an existing, writable parent directory (e.g., `D:\test\projects`).

- **Project Type**: Select `3 — hid/fsa Analyzer`.

- **Project Name**: Enter a name (e.g., `PROVEDIt-demo`).
- Click **Create**.

![Create New Project](docs/images/new-project.png)

### Step 2: Import Capillary Electrophoresis Data

1. In the analysis workspace, click **Open hid/fsa folder** and select the [examples/provedit](examples/provedit) folder.
2. In the upper batch table, verify and adjust the analysis parameters:

| Parameter | Example Value | Note |
| :--- | :--- | :--- |
| **Kit type** | `GlobalFiler_3500` | Applied Biosystems™ GlobalFiler™ 24-locus multiplex |
| **Standard size** | `ABI-LIZ-600-60-TO-460` | GeneScan™ 600 LIZ™ size standard (60–460 bp sizing window) |
| **Threshold** | `50` RFU | Analytical threshold for the bundled example |
| **Initial Type** | `0-Uncertain` | Automatically classified during downstream processing |

![Import Settings](docs/images/import-settings.png)

### Step 3: Automated Genotyping & Artifact Curation

1. Select the batch row and click **AI(P)**.
2. The processing engine performs sizing, ladder alignment, allele calling, and probabilistic artifact filtering across all channels.
3. Upon completion, the lower table displays sample status, contributor classification, and quality indicators:

![Batch Results](docs/images/batch-results.png)

- **Status**: Reports **`Success`** for all profiles.

- **Routing**: Single-source profiles are classified as `Single`. The allelic ladder is routed as `Mixture` (internal calibration flag, not a biological contributor count).

- **Quality**: The 0.5000 ng and 0.0625 ng profiles show green quality symbols; the 0.0078 ng profile has a different indicator. These symbols and Success status do not independently establish complete allele recovery or genotyping accuracy; inspect the traces and reference genotypes.

### Step 4: Electropherogram Inspection & Export

1. Highlight any sample row and click **View Profile** to open the interactive 5-dye electropherogram viewer.
2. Inspect allelic bins, individual peak heights, and automated artifact removal.
3. Click **Export** to save genotype tables. Exported `.txt` files conform to standard forensic table layouts (`Sample Name`, `Marker`, `Allele`, `Size`, `Height`). Reference outputs are provided in [examples/observed-output](examples/observed-output).

---

## License

ACE is distributed as compiled proprietary software and requires software-owner authorization. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for dependency notices and data terms.

## Data Attribution & Citation

The demonstration profiles were derived from the open-access **PROVEDIt** resource:
> Alfonse LE, Garrett AD, Lun DS, Duffy KR, Grgicak CM. A large-scale dataset of single and mixed-source short tandem repeat profiles to inform human identification strategies: PROVEDIt. *Forensic Science International: Genetics*. 2018;32:62–70. [doi:10.1016/j.fsigen.2017.10.006](https://doi.org/10.1016/j.fsigen.2017.10.006).

Official data repository: [PROVEDIt Database, Rutgers University](https://lftdi.camden.rutgers.edu/provedit/files/).

---

## Repository Structure

```text
├── README.md               # Master English documentation
├── THIRD_PARTY_NOTICES.md  # Third-party component licenses & data terms
├── docs/
│   ├── USER_GUIDE.md       # Detailed software operations & troubleshooting
│   ├── VERIFICATION.md     # Demonstration run and known observations
│   └── images/             # Application & electropherogram screenshots
└── examples/
    ├── provedit/           # Curated PROVEDIt raw HID profiles & manifest
    └── observed-output/    # Example exported genotype tables
```
