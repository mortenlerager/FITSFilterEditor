# FITSFilterEditor
A lightweight Windows tool for adding or updating filter names in FITS headers and filenames. Designed for ZWO ASIAIR astrophotography files, with batch processing, customizable filters, and preservation of original file timestamps. No Java installation required.

# FITS Filter Editor

A lightweight Windows utility for adding or updating filter information in FITS files captured with ZWO ASIAIR.

When using ASIAIR without an electronic filter wheel, the filter name may be missing from both the FITS header and the filename. FITS Filter Editor solves this problem, allowing astrophotography software such as PixInsight WeightedBatchPreprocessing (WBPP) to recognize and group images by filter.

## Features

- Adds or updates the `FILTER` keyword in FITS headers.
- Inserts the filter name into the filename following the ASIAIR naming convention.
- Supports batch processing of multiple FITS files.
- Includes three configurable filter presets and a custom filter field.
- Preserves original file timestamps.
- Prevents duplicate filter names in filenames.
- Remembers the last selected folder.
- Configurable file dialog size and font size.
- Runs on Windows without requiring a separate Java installation.

## Example

Original filename:

```text
Light_NGC 772_180.0s_Bin1_294MC_gain120_20261029-214001_1deg_-10.0C_0001.fit
```

After selecting `Lpro`:

```text
Light_NGC 772_180.0s_Bin1_294MC_Lpro_gain120_20261029-214001_1deg_-10.0C_0001.fit
```

The FITS header is updated with:

```text
FILTER  = 'Lpro'
```

PixInsight WBPP can then identify and group the frames by their filter.

## Installation

1. Download the ZIP file from the GitHub Releases section.
2. Extract the ZIP file to a folder of your choice.
3. Open the `FITSFilterEditor` folder.
4. Double-click `FITSFilterEditor.exe`.

No installation or separate Java runtime is required.

**Important:** Keep the `app` and `runtime` folders together with the executable.

## Usage

1. Start FITS Filter Editor.
2. Select a filter preset (`Lpro`, `HOO`, `SOO`) or enter a custom filter name.
3. Click **Vælg FITS-filer** (Select FITS files).
4. Select one or more FITS files using Ctrl+A, Ctrl+click, or Shift+click.
5. Click **Opdater valgte FITS-filer** (Update selected FITS files).
6. Review the processing results.

Files are modified directly. No backup copies are created.

**Recommendation:** Test the program on copies of your FITS files before processing important data.

## Configuration

The `FITSFilterEditor.ini` file contains user-editable settings:

```ini
FileDialogHeight=700
FileDialogWidth=1100
Filter1=Lpro
Filter2=HOO
Filter3=SOO
FontSize=14
LastFolder=
```

You can change the three filter presets, font size, and file dialog dimensions.

`LastFolder` is updated automatically when selecting files. If empty or invalid, the program uses a default folder.

Edit the INI file while the program is closed.

## Compatibility

- Windows
- ZWO ASIAIR FITS files
- PixInsight / WeightedBatchPreprocessing (WBPP)
- Bundled Java runtime

## Notes

FITS Filter Editor preserves the image data while updating the FITS header and filename.

The original file timestamps are restored after processing.

The utility is intended primarily for FITS files following the ASIAIR filename convention.

## Author

© 2026 Morten Lerager / Denmark

Version 1.4
