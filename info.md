## Fork U – House Card

Glassmorphism weather dashboard that blends live meteorological data with custom house renders.

- **Storyteller advisor** translates forecast, wind chill, UV, AQI and pollen readings into contextual messages.
- **Dynamic weather art** swaps your AI-generated house images per season, day/night cycle and fog/rain states.
- **Room badges** let you overlay temperature sensors on precise locations around the building.
- **Party / gaming mode** adds ambient lighting and synthwave overlays on demand.

### Requirements

- Home Assistant `2024.2` or newer.
- Weather, season and sun entities (`weather.*`, `sensor.season`, `sun.sun`).
- Optional: UV, AQI, pollen, wind speed/direction sensors for enriched advice.
- Provide PNG/JPG renders of your house for each season and effect you want to showcase.

### Installation

1. Install through HACS (`Frontend` category) and reload resources.
2. Ensure `/hacsfiles/fork_u-house_card/fork_u-house_card.js` is referenced under `extra_module_url`.
3. Configure the card:

```yaml
type: custom:fork-u-house-card
weather_entity: weather.home
season_entity: sensor.season
sun_entity: sun.sun
```

Add your room sensors under `rooms:` with `x`/`y` coordinates to position the badges over the artwork.

### Tips

- Use `test_weather_state` to preview rain, fog or lightning without waiting for real data.
- Keep image filenames consistent (`winter_day.png`, `winter_night.png`, etc.) to simplify automation.
- See README for full YAML examples, performance notes and prompt ideas for generating artwork.
