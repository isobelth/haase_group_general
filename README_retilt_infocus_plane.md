# retilt_infocus_plane

This notebook retilts microscopy z-stacks to flatten a curved in-focus plane across the field of view.

## What it does

- Accepts an input that is either:
  - a single `.tif`/`.tiff`
  - a single `.lif` (processes all images in that file)
  - a folder containing `.tif`, `.tiff`, and/or `.lif`
- Supports two focus modes:
  - `"brightfield"` (Retilts based on estimation of the most in focus plane)
  - `"fluorescence"` (Retilts based on where there is most fluorescence)
- Saves outputs as TIFF named:
  - `<original_name>_retilted.tif`
- Writes ImageJ/Fiji-compatible hyperstacks in axis order `ZCYX`.

### Parameters

- `input_path`: file or folder to process.
- `output_dir`: destination folder for retilted TIFFs.
- `focus_channel`: channel index used to estimate the focus plane (so if you pick brightfield, select the brightfield index, or fluorescence for fluorescence mode).
- `focus_mode`: `"brightfield"` or `"fluorescence"`.
- `overwrite`: whether to replace existing output files.
