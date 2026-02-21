# Przewodnik Generowania Grafik Domu (Fork U-House Card)

Cała logika generowania (prompty, style, obsługa API) znajduje się w skrypcie:
`generate_house_images_v4.py`

## 1. Wymagania
- Python zainstalowany w systemie.
- Zainstalowana biblioteka: `pip install google-generativeai`
- Klucz API (jest zaszyty w skrypcie, ale upewnij się, że jest aktywny).

## 2. Jak uruchomić generowanie?

Otwórz terminal w folderze projektu i wpisz odpowiednią komendę w zależności od tego, co chcesz uzyskać.

### A. Pełna seria V4 (Standardowa jakość / Preview)
Generuje pory roku, pory dnia i pogodę.
```powershell
python "C:\cards_development\fork_u-house_card_repo\image_generation\generate_house_images_v4.py" --phase v4
```

### B. Pełna seria V5 (Alternatywna wersja)
Jeśli wersja V4 ci się nie podoba, uruchom to, aby uzyskać inne warianty.
```powershell
python "C:\cards_development\fork_u-house_card_repo\image_generation\generate_house_images_v4.py" --phase v5
```

### C. Tylko tryby Gamingowe (5 wariantów specjalnych)
Cyberpunk, Matrix, Mario, Xbox Kid, Synthwave.
```powershell
python "C:\cards_development\fork_u-house_card_repo\image_generation\generate_house_images_v4.py" --phase gaming
```

### D. Generowanie nowego Mastera (Wzorca)
Użyj tego TYLKO jeśli chcesz zmienić główny wygląd domu (kąt, bryłę). Wszystkie inne warianty będą dziedziczyć kształt z tego pliku.
```powershell
python "C:\cards_development\fork_u-house_card_repo\image_generation\generate_house_images_v4.py" --phase master
```

---

## 3. Zmiana Modelu AI (Flash vs Pro)

W pliku `generate_house_images_v4.py` (linia ok. 250-260) możesz zmienić model:

**Dla najwyższej jakości (ale limitowany dzienny dostęp):**
Zmień zmienną `preview_model` na:
```python
preview_model = "models/gemini-3-pro-image-preview"
```

**Dla szybkości i braku limitów (obecnie ustawiony):**
Zmień zmienną `preview_model` na:
```python
preview_model = "models/gemini-2.5-flash-image"
```

---

## 4. Gdzie szukać plików?
Wygenerowane pliki trafiają do folderów:
- `out_gemini-3-pro-image-preview---v4`
- `out_gemini-3-pro-image-preview---v5`
