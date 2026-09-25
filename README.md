# Tips Dataset: Matplotlib vs Seaborn

A side-by-side practice project comparing Matplotlib and Seaborn syntax using
Seaborn's built-in `tips` dataset. The goal isn't analysis — it's getting
comfortable with how each library approaches the same chart.

## Requirements

```bash
pip install pandas matplotlib seaborn
```

## Usage

```bash
python tips_charts.py
```

This loads the dataset, prints a quick preview, and generates 5 PNG files,
each showing a Matplotlib version (left) and Seaborn version (right) of the
same chart.

## Charts

| File | Chart | Matplotlib | Seaborn |
|---|---|---|---|
| `01_histogram.png` | Distribution of `total_bill` | `ax.hist()` | `sns.histplot()` with KDE overlay |
| `02_barchart.png` | Average bill by day | `ax.bar()` | `sns.barplot()` |
| `03_boxplot.png` | Bill spread by day | `ax.boxplot()` | `sns.boxplot()`, also split by `smoker` |
| `04_scatterplot.png` | Bill vs. tip | `ax.scatter()` colored/sized by party size | `sns.scatterplot()` with `hue`/`style`/`size` |
| `05_heatmap.png` | Correlation matrix | `ax.imshow()` + manual cell annotations | `sns.heatmap()` |

## Notes

- Both sides use the `viridis` palette where relevant, for a fair comparison.
- Seaborn generally needs fewer lines for the same result — Matplotlib gives
  more manual control (e.g. the heatmap annotations, colorbar placement).
- All figures use custom titles, axis labels, and font sizes rather than
  library defaults.

## Dataset

`tips` — 244 rows of restaurant bills: `total_bill`, `tip`, `sex`, `smoker`,
`day`, `time`, `size`. Ships with Seaborn via `sns.load_dataset("tips")`.
