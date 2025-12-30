A complete custody dashboard including:

✅ Last night result

✅ Manual night correction

✅ Total nights comparison (MTD + YTD)

✅ Scheduled vs Actual (MTD)

✅ Scheduled vs Actual (YTD)

✅ Custody percentages (MTD + YTD)

✅ Rolling 14-night visual history bar

This dashboard is designed to work out of the box with the blueprints and sensors package in this repository.

⚠️ IMPORTANT: Entity Naming

This dashboard assumes you used the standard helper and counter names shown in the video and listed below.

If you renamed entities, you will need to update the dashboard YAML manually.

Required helper entities
input_select.custody_night_location_auto
input_select.custody_night_location_final
input_boolean.custody_night_locked
input_boolean.custody_night_counted
input_boolean.custody_night_manual_override
input_text.custody_other_reason
input_text.custody_last_final_display_date
input_text.custody_last_counted_date
input_text.custody_last_counted_location
input_text.custody_history_14

Required counters
counter.custody_nights_dad
counter.custody_nights_mom
counter.custody_nights_other

counter.custody_nights_dad_mtd
counter.custody_nights_mom_mtd
counter.custody_nights_other_mtd

Required sensors

(created by packages/custody_sensors.yaml)

sensor.custody_final_night_with_date
sensor.custody_history_14_icons
sensor.custody_ytd_total_nights
sensor.custody_mtd_total_nights

sensor.custody_expected_dad_nights_ytd
sensor.custody_expected_dad_nights_mtd
sensor.custody_dad_variance_ytd
sensor.custody_dad_variance_mtd

sensor.custody_dad_pct_ytd
sensor.custody_mom_pct_ytd
sensor.custody_other_pct_ytd
sensor.custody_dad_pct_mtd
sensor.custody_mom_pct_mtd
sensor.custody_other_pct_mtd

🛠️ How to install the dashboard

Open Home Assistant

Go to Dashboard

Click Edit Dashboard

Click Add Card

Choose Manual

Copy the contents of:

dashboards/dashboard_package_full.yaml


Paste into the editor

Click Save

That’s it.

🧠 How this dashboard is meant to be used

Day-to-day:
Look at Last Night Result and the 14-night history bar

Corrections:
Use Manual Night Correction (turn override ON, adjust Final, add reason if Other)

Monthly review:
Check Scheduled vs Actual (MTD) and Custody % (MTD)

Yearly review / reporting:
Use YTD totals, percentages, and Google Sheets exports

The system is intentionally designed to be:

boring

repeatable

emotion-free

defensible
