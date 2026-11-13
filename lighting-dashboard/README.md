# Modern Lighting Dashboard for Home Assistant

Views: **Overview** (all on/off, night preset, master brightness, automation toggles, room tiles) plus one view per room
(Living Room, Kitchen, Bedroom, Office) with brightness, color, and white-temperature controls.

## Install
1. In HACS, install **Mushroom** and **card-mod** (Frontend).
2. Copy `themes/modern_lighting.yaml` to `/config/themes/` and make sure `configuration.yaml` has:
   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```
   Restart / reload themes, then pick **modern_lighting** in your profile (it follows light/dark automatically).
3. Settings → Dashboards → Add Dashboard → "New dashboard from scratch", URL `lovelace-lighting`.
   Open it, ⋮ → Edit → ⋮ → Raw configuration editor, paste `dashboard.yaml`.
4. Replace the placeholder entity IDs (`light.living_room_ceiling`, `automation.motion_lights`, …) with yours.
   If you use a different dashboard URL, update the `navigation_path` values.
5. For "All lights" master slider, create a light group helper (Settings → Helpers → Group → Light group) and use its entity ID in place of `group.all_lights`.
