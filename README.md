# O3 Knapsack QAOA Benchmark

An interactive, responsive 0/1 knapsack solver and educational QAOA benchmark based on the **Qiskit Fall Fest 2026 O3 Knapsack** presentation.

## Features
- Edit item names, values, weights, and capacity.
- Add and remove items (up to 18 for exact exhaustive solving).
- Import JSON by pasting it or selecting a local `.json` file.
- Export the current problem as JSON.
- Select a bag manually or load the optimal feasible combination.
- Rank the five highest-value legal combinations for the current dataset.
- Explore QUBO/QAOA concepts and the presentation's processor topology metrics.
- Responsive dark research-console interface; no framework or build step required.

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
The custom-data optimizer enumerates subsets classically and exactly (up to 18 items, or 262,144 subsets). The QUBO/QAOA panel is an educational explanation, and processor values are reported from the source presentation. This site does **not** execute Qiskit circuits or connect to real quantum hardware.

## GitHub Pages
1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then save.
4. After deployment completes, the site URL will appear on that settings page.

## License
Add a license if you want to specify how others may reuse the project.
