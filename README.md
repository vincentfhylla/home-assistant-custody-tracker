🧠 Home Assistant Custody Tracker
Dad / Mom / Other — Automations, Dashboards, Forecasting & Reports

This project is a production-ready custody tracking system for Home Assistant, designed for divorced and co-parenting parents who want:

✅ Accurate overnight custody tracking

✅ Zero emotion, zero arguments

✅ Automatic logging (no spreadsheets at midnight)

✅ Court-defensible history & reports

✅ Clear monthly and yearly summaries

It uses zones, time-based locking, blueprints, dashboards, and optional Google Sheets logging to track custody nights cleanly and reliably.

🎯 Why this exists

It’s a new year — and honestly, this is the best time to start tracking custody nights correctly.

Once you get a few months into the year, you’re stuck reconstructing nights from:

texts

calendars

screenshots

and memory

This system removes all of that.

You just enjoy your time with your kid.
Home Assistant handles the record-keeping.

🧩 What’s included
✅ Blueprints (Automations)

Reusable, restart-safe automations that handle the logic:

Night auto-detect (zone-based)

Night finalize + lock

Daily reset

These are intentionally simple:

Dad

Mom

Other

No fragile device trackers.
No guessing.
No double-counting.

📁 blueprints/automation/

✅ Sensors & Math (Packages)

All calculations live in one place:

14-night rolling history

Custody percentages (MTD / YTD)

Scheduled vs actual comparisons

Variance tracking

Forecasted expected nights

📁 packages/custody_sensors.yaml

✅ Dashboards

A complete, copy-paste dashboard package:

Last night result

Manual night correction

Scheduled vs Actual (MTD)

Scheduled vs Actual (YTD)

Total nights comparison

Custody % (MTD & YTD)

Rolling 14-night visual history bar

📁 dashboards/dashboard_package_full.yaml

Dashboards are not blueprints, so they are pasted manually.

✅ Optional Google Sheets Logging

For:

long-term records

sharing with attorneys

printable reports

backup outside Home Assistant

Uses a simple rest_command.

📂 Repository structure
home-assistant-custody-tracker/
├── README.md                      ← you are here
├── blueprints/
│   └── automation/
│       ├── custody_daily_reset_dad_mom.yaml
│       ├── custody_night_auto_detect.yaml
│       └── custody_night_finalize_dad_mom_other.yaml
├── packages/
│   └── custody_sensors.yaml
├── dashboards/
│   ├── README.md
│   └── dashboard_package_full.yaml

🚀 Quick start (recommended order)
1️⃣ Install the blueprints

Home Assistant → Settings → Automations & Scenes → Blueprints → Import Blueprint

Paste these URLs one at a time:

https://raw.githubusercontent.com/vincentfhylla/home-assistant-custody-tracker/main/blueprints/automation/custody_daily_reset_dad_mom.yaml
https://raw.githubusercontent.com/vincentfhylla/home-assistant-custody-tracker/main/blueprints/automation/custody_night_auto_detect.yaml
https://raw.githubusercontent.com/vincentfhylla/home-assistant-custody-tracker/main/blueprints/automation/custody_night_finalize_dad_mom_other.yaml


Then create automations from each blueprint.

2️⃣ Create helpers & counters

The video walks through this step-by-step.

You’ll create:

input_booleans

input_selects

input_texts

counters (YTD + MTD)

👉 Entity names matter — dashboards and sensors assume standard names.

3️⃣ Install sensors package

Add this to your configuration.yaml if you don’t already use packages:

homeassistant:
  packages: !include_dir_named packages


Then drop in:

packages/custody_sensors.yaml


Restart Home Assistant.

4️⃣ Add the dashboard

Go to:
Dashboard → Edit → Add Card → Manual

Paste:

dashboards/dashboard_package_full.yaml


Save.

5️⃣ (Optional) Enable Google Sheets logging

Set up a Google Apps Script endpoint and connect it using rest_command.

This allows:

automatic logging

printable reports

external backups

🧠 How the system works (high level)

Night auto-detect watches zones overnight

Finalize automation locks the night at a set time

Once locked:

counters increment

history updates

dashboard refreshes

Manual override exists for edge cases

Daily reset prepares the next night

Sensors compute everything else

Once set up, you do nothing.

⚖️ Designed for real life

This system is:

restart-safe

idempotent

boring (on purpose)

emotionally neutral

defensible if ever questioned

It’s not about winning arguments.
It’s about never having them.

🎥 Full walkthrough video

This entire system is built step-by-step in one complete video:

Home Assistant Custody Tracker
Blueprints + Dashboards + Forecasting + Google Sheets

The video includes:

real explanations

real mistakes

real fixes

real co-parenting context

🤝 Contributing / adapting

Feel free to:

fork

simplify

extend

localize

adapt for other custody structures

If you improve it, submit a PR.

⚠️ Disclaimer

This project is not legal advice.
It is a tool for personal record-keeping.

Always consult an attorney for legal matters.
