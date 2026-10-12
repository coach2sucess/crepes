# Crêpes à Latte CEO Cockpit

A one-page health dashboard built from the **CEO Cockpit** tab of `v4_Crepes_Goals_Dashboard.xlsx`.

- `index.html` – the dashboard, prepared for Robin Cardoso (President). **Cockpit** opens with a plain-language bottom line, then the health score, Red/Yellow attention list, every section (each metric has a "How it's measured" drill-down with thresholds, exact figures and source) and blind spots. **By leader** groups metrics by accountable leader for 1:1 prep. **Update data** is the editable grid; every change recalculates statuses immediately.
- `cockpit-data.json` – the metrics the page loads (current value, target, direction, tolerance band, owner, notes).

## Status rule (same as the workbook)
- Higher-is-better: Green if value ≥ target, Yellow if within the band below target, otherwise Red.
- Lower-is-better: Green if value ≤ target, Yellow if within the band above target, otherwise Red.
- Standard band 20%; alternate band 50% for Revenue vs Plan, Net New Revenue, Revenue Erosion, Organic Growth and Bi-Annual Reviews. Both are editable.
- A status picked by hand (for metrics with no number yet) overrides the rule.

## History, freshness and actions
- The Cockpit is organized by the five health areas from the sheet. Each area has its score and verdict, a distance-from-target chart, what needs attention, what is going well, open actions, and a collapsible list of every metric with method, trend and readings.
- Each "Save for everyone" records a dated snapshot (artifact database, `snapshots/<date>`). Trend lines and Improving/Worsening labels come from those snapshots, so they appear once a metric has two readings.
- Every metric has an "as of" date. Editing a value stamps today; numbers older than the stale threshold (default 45 days) are flagged.
- Actions (metric, owner, due date, done) are stored in `actions/<id>` and shared with everyone who can open the page.

- Past readings (Update data tab) backfill history per metric (`readings/<metric>_<date>`), so trend lines can appear before months of saves. The company health score trend uses each metric's latest reading on each date and skips dates where fewer than half the rated metrics have one.
- "What's going well" lists Green metrics by margin over target and any non-Green metric that improved since its last reading.

## Updating
- Edit numbers in the sheet tab and press **Save for everyone** (published artifact), or
- **Import updated .xlsx**: reads the CEO Cockpit tab of the workbook, or
- **Download as .xlsx** exports the cockpit in the original layout with live formulas.

Opened locally, saves stay in that browser.
