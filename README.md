# VizLab - Research Visualization Maker

Paste research data, pick a chart, and export a publication-ready figure as PNG or SVG.
VizLab is a no server, no build step, no dependencies, no account and no upload. Everything runs locally in your browser.

## Features

- **12 chart types:** line, area, bar, grouped bar, stacked bar, scatter, bubble, pie, donut, lollipop, dumbbell and heatmap.
- **CSV or JSON input:** paste data straight into the editor. The preview updates as you type.
- **Overlap-free labels:** value labels are placed after the chart is drawn. They avoid axis text, markers, lines, bars, the legend and each other, and are hidden when there is no free spot.
- **Draggable legend:** drag it to any side of the graph and it snaps there, reserving space so it never covers the plot. Buttons above the graph (◀ ▲ ▼ ▶ and Reset) do the same from the keyboard.
- **Readability controls next to the graph:** font size (70–150%) and zoom (75–160%), each with −, + and Default.
- **Export options:** PNG (2× resolution) or SVG. A dialog lets you include the Title, Subtitle and Caption (all, none or any combination).
- **Themes and fonts:** Editorial, Ink, Paper and Dark themes; Modern Sans or Academic Serif.
- **Help tooltips:** every section and control has a `?` icon with a tooltip, shown on hover or keyboard focus and dismissible with Escape.
- **Glass UI and click particles:** frosted-glass fields and a small particle burst on button clicks. The particles are disabled if your system is set to reduce motion.

## Quick start

1. Download or clone this repository.
2. Open the index.html and redirect to the editor.
3. Click **Load sample**, or paste your own data.
4. Choose a chart type, an X / row field and one or more series.
5. Adjust the title, theme and legend, then click **Export PNG** or **Export SVG**.

## Data format

**CSV**: the first row is the header.

```csv
Horizon,History,Full
30,0.0963,0.0785
60,0.1587,0.1176
90,0.2080,0.2171
```

**JSON**: an array of objects with the same keys in each row.

```json
[
  {"Horizon": 30, "History": 0.0963, "Full": 0.0785},
  {"Horizon": 60, "History": 0.1587, "Full": 0.1176}
]
```

The first column is used as the X / row field by default. Every other numeric column is selected as a series. Hold Cmd or Ctrl to select several series.

## Choosing a chart

| Goal | Chart |
| --- | --- |
| Trend over time | Line, Area |
| Compare categories | Bar, Grouped bar, Lollipop |
| Composition | Stacked bar, Pie, Donut |
| Relationship between values | Scatter, Bubble |
| Paired change | Dumbbell (needs at least two series) |
| Matrix of values | Heatmap |

Pie and donut charts use the first selected series. Scatter and bubble charts need numeric fields. Heatmap and lollipop charts do not show a legend.

## Controls

| Section | What it does |
| --- | --- |
| 1 · Data | Paste CSV or JSON; load the CSV or JSON example |
| 2 · Chart | Chart type, X / row field, series / value fields |
| 3 · Presentation | Title, Y-axis label, subtitle, caption |
| 4 · Style | Theme, font, show values / grid / legend |
| 5 · Dimensions | Figure width (500–2400 px) and height (350–1600 px) |
| 6 · Readability | Smart label placement |
| Graph toolbar | Font size, zoom, legend position |

The header has **Load sample**, **Reset** (restores the defaults), **Export PNG** and **Export SVG**.

## Exporting

Clicking either export button opens a dialog with tick boxes for **Title**, **Subtitle** and **Caption**, plus **Select all** and **Select none**. The title and subtitle are added above the graph and the caption below it. The figure grows taller to fit them, and long text wraps. With nothing ticked, only the graph is exported. The export uses the current theme, font and legend position.

## Accessibility

- All controls are native, keyboard-reachable elements with labels.
- Help icons are buttons linked to their tooltip text (`aria-describedby`, `role="tooltip"`), and Escape dismisses an open tooltip.
- The legend can be moved with buttons as well as by dragging.
- Motion effects respect `prefers-reduced-motion`.

## Browser support

Any current version of Chrome, Edge, Firefox or Safari. The page uses the `<dialog>` element, SVG, pointer events and `backdrop-filter`. Browsers without `backdrop-filter` fall back to solid backgrounds.

## License

Add a license of your choice (for example MIT) as a `LICENSE` file.

## Author

© Rakshit Dogra
