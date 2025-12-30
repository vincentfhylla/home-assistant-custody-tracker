# Home Assistant Custody Tracker (Dad / Mom / Other)

This project tracks custody nights automatically in Home Assistant using:
- Person + Zones
- Restart-safe finalize window
- Manual override (safe, no double counting)
- 14-night rolling history
- Dashboard packages (copy/paste)
- Optional Google Sheets logging + forecasting + printable reporting

## 1) Import the 3 Blueprints

Home Assistant → Settings → Automations & Scenes → Blueprints → Import Blueprint  
Paste these RAW links:

1) Daily Reset (Dad/Mom)
https://raw.githubusercontent.com/vincentfhylla/home-assistant-custody-tracker/main/blueprints/automation/custody_daily_reset_dad_mom.yaml

2) Night Auto Detect
https://raw.githubusercontent.com/vincentfhylla/home-assistant-custody-tracker/main/blueprints/automation/custody_night_auto_detect.yaml

3) Night Finalize (Dad/Mom/Other)
https://raw.githubusercontent.com/vincentfhylla/home-assistant-custody-tracker/main/blueprints/automation/custody_night_finalize_dad_mom_other.yaml

## 2) Standard Entity Names (Recommended)

To make the Dashboard Package work with one paste, use these helper/counter names:

### Helpers
- input_select.custody_night_location_auto
- input_select.custody_night_location_final
- input_boolean.custody_night_locked
- input_boolean.custody_night_counted
- input_boolean.custody_night_manual_override
- input_text.custody_other_reason
- input_text.custody_last_final_display_date
- input_text.custody_last_counted_date
- input_text.custody_last_counted_location
- input_text.custody_history_14

### Counters
- counter.custody_nights_dad
- counter.custody_nights_mom
- counter.custody_nights_other
- counter.custody_nights_dad_mtd
- counter.custody_nights_mom_mtd
- counter.custody_nights_other_mtd

## 3) Packages (Sensors + Forecasting)

Install the sensors package in:
`/config/packages/custody_sensors.yaml`

Enable packages in `configuration.yaml`:
```yaml
homeassistant:
  packages: !include_dir_named packages
