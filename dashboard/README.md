# Crêpes à Latte CEO Cockpit

A one-page health dashboard built from the **CEO Cockpit** tab of `v4_Crepes_Goals_Dashboard.xlsx`.

- `index.html` – the dashboard. **Cockpit** tab shows the health score, Red/Yellow attention list and every section. **Edit the sheet** tab is an editable grid; every change recalculates statuses immediately.
- `cockpit-data.json` – the metrics the page loads (current value, target, direction, tolerance band, owner, notes).

## Status rule (same as the workbook)
- Higher-is-better: Green if value ≥ target, Yellow if within the band below target, otherwise Red.
- Lower-is-better: Green if value ≤ target, Yellow if within the band above target, otherwise Red.
- Standard band 20%; alternate band 50% for Revenue vs Plan, Net New Revenue, Revenue Erosion, Organic Growth and Bi-Annual Reviews. Both are editable.
- A status picked by hand (for metrics with no number yet) overrides the rule.

## Updating
- Edit numbers in the sheet tab and press **Save for everyone** (published artifact), or
- **Import updated .xlsx**: reads the CEO Cockpit tab of the workbook, or
- **Download as .xlsx** exports the cockpit in the original layout with live formulas.

Opened locally, saves stay in that browser.
