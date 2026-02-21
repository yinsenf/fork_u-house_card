# House Graphics Generation Guide (Fork U-House Card)

This guide explains how to generate isometric house assets using the automated Python script `generate_house_images_v4.py`.

## 1. Prerequisites

- **Python 3.x** installed.
- **Google Generative AI Library**:
  ```bash
  pip install google-generativeai
  ```
- **Reference Images**: Ensure the `reference/` folder contains the necessary master images (e.g., `_master_reference.png` in `master/` folder).

## 2. How to Run

Open your terminal in the project directory (`image_generation/`) and run one of the following commands based on your needs.

### A. Phase V4 (Standard Preview Set)
Generates all seasons, times of day, and weather conditions (rain, snow, fog, lightning).
```bash
python generate_house_images_v4.py --phase v4
```

### B. Phase V5 (Alternative Set)
Generates a second variation of the entire set if the V4 results are not satisfactory.
```bash
python generate_house_images_v4.py --phase v5
```

### C. Gaming Modes (Special Variants)
Generates 5 immersive modes: Cyberpunk, Synthwave, Matrix, Mario Bros, Xbox Kid.
```bash
python generate_house_images_v4.py --phase gaming
```

### D. Generate New Master
**WARNING:** Only use this if you want to completely change the house's angle/shape. All subsequent variants will be based on this new master.
```bash
python generate_house_images_v4.py --phase master
```

---

## 3. Configuring the AI Model

You can switch between speed and quality by editing `generate_house_images_v4.py` (around line 250):

**For Maximum Quality (High Fidelity, stricter quotas):**
```python
preview_model = "models/gemini-3-pro-image-preview"
```

**For Speed & Reliability (Less likely to hit rate limits):**
```python
preview_model = "models/gemini-2.5-flash-image"
```

*Note: If you encounter a 429 Quota Exceeded error, switch to the Flash model or wait for the quota to reset.*

## 4. Output Locations
Generated images will appear in:
- `out_gemini-3-pro-image-preview---v4/`
- `out_gemini-3-pro-image-preview---v5/`
