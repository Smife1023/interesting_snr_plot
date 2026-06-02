# SNR Curve Plotter

A lightweight, browser-based tool for plotting SNR (Signal-to-Noise Ratio) vs. Accuracy curves. No installation required — just open the HTML file and start plotting.

## Features

- **Paste-to-Plot**: Directly paste your `result.json` or TXT data — no file upload needed
- **Auto SNR Extraction**: Automatically finds `"snr_results"` in a full JSON file and extracts the data
- **Auto Percentage Conversion**: Values in 0-1 range are automatically multiplied by 100 for percentage display
- **Multi-Dataset Support**: Add multiple curves to the same chart for comparison
- **Legend Management**: Customize each curve's name, color, line style (solid/dashed/dotted), line width, and marker size
- **Show/Hide Curves**: Toggle individual datasets on/off via checkboxes
- **Interactive Tooltip**: Hover over data points to see SNR value, accuracy, and cross-dataset average
- **Statistics Panel**: Auto-calculated Mean, Std, Min, Max per dataset, plus overall mean across visible datasets
- **Chart Settings**: Customizable X/Y axis titles, grid lines, data markers, and Y-axis range
- **Export Options**: Export as PNG with white, transparent, or custom background color

## Quick Start

1. Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari)
2. Select data type: **JSON** or **TXT**
3. Paste your data into the text area
4. Click **+ Add Data**
5. Repeat to add more curves

## Data Formats

### JSON (`result.json`)

Paste the entire JSON file. The tool auto-extracts `"snr_results"`:

```json
{
  "model_name": "MyModel",
  "snr_results": {
    "-20": 0.095,
    "-18": 0.096,
    "-16": 0.098,
    "-14": 0.132,
    "-12": 0.178,
    "-10": 0.267,
    "-8": 0.404,
    "-6": 0.567,
    "-4": 0.739,
    "-2": 0.859,
    "0": 0.919,
    "2": 0.925,
    "4": 0.927,
    "6": 0.932,
    "8": 0.926,
    "10": 0.932,
    "12": 0.943,
    "14": 0.933,
    "16": 0.929,
    "18": 0.929
  }
}
```

- X values (SNR in dB) are automatically rounded to the nearest integer
- Y values in 0-1 range are auto-converted to percentages (e.g., 0.095 → 9.50%)

### TXT (comma-separated)

One data point per line: `x, y`

```
-19.82, 23.55
-17.99, 23.82
-15.96, 25.49
-13.97, 29.95
-11.93, 37.91
-9.97, 49.49
-7.97, 60.94
-5.97, 72.11
-3.98, 81.32
-1.98, 87.74
0.09, 91.92
2.05, 92.75
4.08, 93.02
6.03, 93.85
8.02, 94.12
10.10, 94.39
12.09, 94.38
14.04, 94.65
16.07, 94.64
18.06, 94.91
```

- X values are rounded to the nearest integer
- Y values are used as-is (treated as percentages)

## Screenshot


## Tech Stack

- **HTML5** + **CSS3** + **Vanilla JavaScript** (zero framework dependencies)
- [Chart.js v4](https://www.chartjs.org/) (loaded via CDN)

## File Structure

```
drawsnr/
└── index.html    # Single-file application (HTML + CSS + JS)
```
