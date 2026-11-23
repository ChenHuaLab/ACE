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

## Known observations

- JavaFX CSS warnings about Pos.left did not prevent the demonstrated analysis.
- The project parent directory must exist.
- The folder chooser selects directories and may not list the individual HID files.
- The ladder classification is a software routing state rather than a biological donor count.
- Success describes processing completion; it does not establish complete allele recovery or forensic validity.

## Reproduce the check

Use [USER_GUIDE.md](USER_GUIDE.md). Exact input files and provenance are in [manifest.csv](../examples/provedit/manifest.csv), and software-generated sample tables are in [observed-output](../examples/observed-output).
