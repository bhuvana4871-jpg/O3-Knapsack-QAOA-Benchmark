# O3 Knapsack QAOA Benchmark

An interactive, responsive 0/1 knapsack solver and educational QAOA benchmark based on the **Qiskit Fall Fest 2026 O3 Knapsack** presentation.

## Features
- Edit item names, values, weights, and capacity.
- Add and remove items (up to 18 for exact exhaustive solving).
- Import JSON by pasting it or selecting a local `.json` file.
- Export the current problem as JSON.
- Select a bag manually or load the optimal feasible combination.
- Rank the five highest-value legal combinations for the current dataset.
- Create custom binary optimization models with editable objective coefficients and linear constraints.
- Use rule-based suggestions to help translate a written problem into a model template.
- Solve and rank feasible assignments for models with up to 18 binary variables.
- Save, reopen, and delete problem instances in a browser-local problem library.
- Explore QUBO/QAOA concepts and the presentation's processor topology metrics.
- Use the Simulation Lab to vary shots, assumed noise, and QAOA depth for an illustrative demo with estimated legal samples, best-bag hits, and nonlegal samples.
- Vintage wedding-editorial palette: espresso, oxblood, dusty rose, antique champagne, parchment, and muted sage.
- Responsive dark research-console interface; no framework or build step required.

## Problem Studio

Open the **Problem studio** tab, describe the problem, review the suggested model, and edit the variable/objective list and constraints. Variables use `name, objective_value`, one per line. Constraints use `name:coefficient, name:coefficient <= limit`; `>=` and `=` are also supported. The solver maximizes the sum of selected objective coefficients subject to all listed constraints. The library is stored in browser `localStorage` on that device; it is not synchronized between browsers and can be cleared with browser storage.

The statement helper is rule-based, not a general-purpose AI model generator. It cannot reliably infer complete mathematical formulations for scheduling, routing, or other arbitrary problem families. Review every variable, coefficient, and constraint before relying on a result.

## Run locally
Open `index.html` in a modern browser. No installation or dependencies are required.

## Data format
Import an object containing capacity and items:

```json
{
  "capacity": 15,
  "items": [
    { "name": "Laptop", "value": 10, "weight": 5 },
    { "name": "Camera", "value": 7, "weight": 4 }
  ]
}
```

You can also import an array of items directly; the current capacity is retained.

## Original O3 example

| Item | Value | Weight |
|---|---:|---:|
| Item 1 | 10 | 5 |
| Item 2 | 4 | 3 |
| Item 3 | 7 | 4 |
| Item 4 | 5 | 2 |
| Item 5 | 8 | 6 |

Capacity: **15**. The best legal combination is Items 1–4, with value **26** and weight **14**.

## Scientific scope
The custom-data optimizer enumerates subsets classically and exactly (up to 18 items, or 262,144 subsets). The Simulation Lab uses a transparent illustrative formula seeded from the presentation-reported 95.9% legal-sample rate and 2.4% best-bag chance at p=2; it applies assumed-noise and depth adjustments to create demo estimates. These generated estimates are **not measured results** and are **not** a Qiskit simulation. The QUBO/QAOA panel is educational, and processor values are reported from the source presentation. This site does **not** execute Qiskit circuits or connect to real quantum hardware.

## GitHub Pages
1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **GitHub Actions** as the source.
3. The workflow at `.github/workflows/deploy-pages.yml` deploys the root static site when you push to `main`.
4. Check the **Actions** tab for a successful `Deploy static app to GitHub Pages` run.

## License
Add a license if you want to specify how others may reuse the project.
