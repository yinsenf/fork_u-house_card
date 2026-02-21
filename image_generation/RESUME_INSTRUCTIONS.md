# Resume Image Generation

## Current State (15.02.2026)
- **Master Image**: Generated new `master/_master_reference.png` using `gemini-2.5-flash-image`.
- **Script**: `generate_house_images_v4.py` updated to use `gemini-2.5-flash-image` due to `gemini-3-pro-image-preview` hitting daily quotas.
- **Samples**: Verified generation with `summer_day_sample.png`, `winter_snowy_day_sample.png`, `autumn_rainy_night_sample.png` in `out_gemini-3-pro-image-preview---v4`.

## Next Steps
To continue generation for the full set (v4 and v5), run the following commands:

### 1. Generate v4 Set (Preview Quality)
```bash
python generate_house_images_v4.py --phase v4
```

### 2. Generate v5 Set (Alternative Version)
```bash
python generate_house_images_v4.py --phase v5
```

### 3. Generate High-Res Versions (When model available)
Currently, `hires` uses a placeholder model name. Once the real model is confirmed/available, update `hires_model` in the script and run:
```bash
python generate_house_images_v4.py --phase hires
```

## Troubleshooting
- If generation fails with 429 (Quota Exceeded), wait until quota resets (usually daily) or switch to another available model in the script (`preview_model` variable).
