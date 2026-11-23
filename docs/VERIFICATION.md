# Example run verification

The bundled PROVEDIt example was tested on Windows on 9 November 2026 using ACE v1.0.

## Functional checks

| Check | Result |
| --- | --- |
| Start ACE with its bundled Java runtime | Passed |
| Existing authorization check | Passed on the local test computer |
| Create an HID/FSA Analyzer project | Passed after creating the parent folder |
| Import the four bundled HID files | Passed; one imported batch |
| Settings | GlobalFiler_3500; ABI-LIZ-600-60-TO-460; 50 RFU; 0-Uncertain |
| Analyze the batch | Passed; four result records |
| Result status | Four Success records |
| Sample routing | Three samples Single; ladder displayed as Mixture |
| Write TXT/ALL/CHANGES outputs | Passed |
| Open the multichannel profile viewer | Passed in the ACE v1.0 run |
| Application version | Welcome title and footer display ACE v1.0 |

All four records completed processing, and the multichannel profile viewer opened successfully. Screenshots in [images](images) show the loading screen, welcome screen, project creation, import settings, completed batch and profile viewer. Generated sample TXT tables are included in [observed-output](../examples/observed-output).

The interactive demonstration displayed a 2 s batch runtime. This observation covers four records, including a ladder, and excludes installation and import; it is not a hardware-independent performance claim.

## Single-file launcher checks

The `ACE.exe` distribution was tested on Windows on **23 November 2026**. The application is available from [Figshare](https://figshare.com/s/a3ac90e47f505f1912c1). ACE is developed in Java and C. The final launcher updates preserved the tested Java core and native library.

| Check | Result |
| --- | --- |
| Four bundled PROVEDIt HID inputs with the packaged core | Four Success records; generated TXT files matched the earlier verified outputs byte for byte |
| First-run program-folder selection | Passed |
| Direct program folder and sibling default results folder | Passed; selecting `D:\ACE` corresponds to `D:\ACE` and `D:\ACE_results` |
| Chinese characters and spaces in the selected path | Passed with the actual EXE |
| Remember the selected folder and launch again | Passed; no repeated prompt or extraction |
| Retain existing results on the next launch | Passed |
| Cancel before preparation | Passed; no extraction or saved choice |
| Invalid saved path and unavailable settings storage | Recoverable selection; application continued when settings could not be saved |
| High-DPI folder window and embedded icon | Passed at 150% display scaling; the 720 × 466 design client area scaled to 1080 × 699 pixels |

These results cover the tested inputs and launcher behavior. They do not establish complete allele recovery or validate every application function.

## Known observations

- JavaFX CSS warnings about Pos.left did not prevent the demonstrated analysis.
- The project parent directory must exist.
- The folder chooser selects directories and may not list the individual HID files.
- The ladder classification is a software routing state rather than a biological donor count.
- Success describes processing completion; it does not establish complete allele recovery or forensic validity.

## Reproduce the check

Use [USER_GUIDE.md](USER_GUIDE.md). Exact input files and provenance are in [manifest.csv](../examples/provedit/manifest.csv), and software-generated sample tables are in [observed-output](../examples/observed-output).

