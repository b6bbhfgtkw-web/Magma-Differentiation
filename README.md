# Magma Differentiation Visualizer (Fractional Crystallization)

A static, browser-based teaching tool for visualizing **magma differentiation by fractional crystallization**. Students advance **step-by-step** through a predefined crystallization sequence and watch how the **melt composition** and **crystal assemblage** evolve.

This project is based on the cation-count (M&M) magma chamber lab format and the crystallization schedule / parent melt totals used in the accompanying spreadsheet. 

---

## Key learning goals

- Connect **mineral crystallization** to **systematic melt evolution**.
- Reinforce **stoichiometry** and “what gets removed” from the melt at each step.
- Interpret changing composition using visualizations that update immediately.

---

## What students can do

- Advance **one crystallization step at a time** (jump-ahead is disabled).
- Observe melt composition updates after each step.
- View **per-cation line charts** (one chart per cation) that grow only as far as the step reached.
  - **Si chart uses 0–100% y-axis**; all other cations use **0–50%**.
- View a **pie chart** of normalized mineral modes (ol / pyx / plag / alk / qtz) for the currently selected step.
- Use the **Magma Visualizer** (stacked color bar) showing the partition of the total magma into:
  - remaining **melt**, plus
  - **cumulative crystals by mineral**.

---

## Instructor features

- Edit the **initial melt cations** (Si, Ti, Al, Fe, Mg, Ca, Na, K) in the UI.
- **Limiting-reagent behavior** (important!): if a required element runs out, minerals in that step crystallize only as much as the melt can supply.
  - Prevents negative cation counts.
  - Prevents percent values >100%.
- “Minerals crystallized” table shows **Actual vs Requested** counts so students can see where the melt becomes limiting.

---

## How the model works (transparent assumptions)

- The melt starts with a user-editable **cation inventory**.
- Each step requests certain mineral amounts.
- For each mineral, the app checks whether the melt contains enough of each required element.
  - The mineral amount is limited by the **first element to run out** (limiting reagent), and only that feasible amount crystallizes.
- Melt composition is recomputed after each step.

> Note: The Magma Visualizer percentages are computed on a **cation-total basis** (remaining melt cations + cations locked into each mineral cumulatively). This keeps the mass-balance internally consistent with the rest of the cation-count model.

---

## Repository structure (recommended for GitHub Pages)

```
.
├── docs/
│   ├── index.html        # the app (single page)
│   └── .nojekyll         # disables Jekyll processing (static files served as-is)
└── README.md
```

---

## Run locally

No installation required.

1. Download/clone the repository.
2. Open `docs/index.html` in a modern browser (Chrome/Edge/Firefox).

---

## Dependencies / offline use

- The app loads **Chart.js** from a CDN by default.
- For fully offline classroom use, download Chart.js and update the `<script src="...">` tag in `docs/index.html` to point to your local file.

---

## Customization tips

- **Change the parent melt:** use the initial cation inputs, then click **Apply**.
- **Create alternative problem sets:** edit the crystallization schedule arrays in `docs/index.html` (the `CRYSTALLIZATION` object).
- **Change colors:** edit `MINERAL_COLORS` (magma visualizer) and the cation color mapping.

---

## License

Free to use and modify as needed.

---

## Credits

Built to support petrology instruction and visualization of fractional crystallization trends.
