# bzUI
bzUI


# @bonezegei/bzui

bzUI (Bonezegei UI) is a small set of front-end assets:

- **bzChart.js**: a canvas chart engine (bar, line, spline, area, candlestick, mixed, donut, and more)
- **bzui.css**: design tokens (light and dark themes), base styles, and chart utilities
- **bzui-animations.css**: keyframe animations
- **Bonezegei.js**: the reactive library the rest of the bzUI ecosystem is built on

The chart and CSS files have no external dependencies. No CDNs, fonts, or frameworks are required.

## Installation

```bash
npm install @bonezegei/bzui
```

## Usage

### Styles

```html
<link rel="stylesheet" href="node_modules/@bonezegei/bzui/dist/bzui.min.css">
<link rel="stylesheet" href="node_modules/@bonezegei/bzui/dist/bzui-animations.min.css">
```

Or from a bundler:

```js
import '@bonezegei/bzui/css';
import '@bonezegei/bzui/css/animations';
```

### Charts

```html
<canvas id="sales" width="600" height="300"></canvas>
```

```js
import { BzChart } from '@bonezegei/bzui/chart';

const chart = new BzChart(document.querySelector('#sales'), { type: 'bar' });

chart.setData({
  labels: ['Jan', 'Feb', 'Mar'],
  datasets: [{ label: 'Sales', data: [12, 19, 7] }]
});

chart.setData({ type: 'line' });  // change type on the same chart
chart.destroy();
```

Chart colours come from the `--bz-chart-color-1` to `--bz-chart-color-8`, `--bz-chart-grid`, and `--bz-chart-text` CSS variables. Load `bzui.css` so the chart follows the theme. Without it, `bzChart` uses a built-in fallback palette.

### Bonezegei.js

```js
import { Bonezegei } from '@bonezegei/bzui/bonezegei';
```

## Package exports

| Import path | File |
| ----------- | ---- |
| `@bonezegei/bzui` and `@bonezegei/bzui/chart` | `dist/bzChart.min.js` |
| `@bonezegei/bzui/css` | `dist/bzui.min.css` |
| `@bonezegei/bzui/css/animations` | `dist/bzui-animations.min.css` |
| `@bonezegei/bzui/css/components` | `dist/bzui-components.min.css` |
| `@bonezegei/bzui/css/utilities` | `dist/bzui-utilities.min.css` |
| `@bonezegei/bzui/css/extended` | `dist/bzui-extended.min.css` |
| `@bonezegei/bzui/css/icons` | `dist/bzui-icons.min.css` |
| `@bonezegei/bzui/bonezegei` | `dist/Bonezegei.min.js` |

All files are minified ES modules or CSS. Readable sources are in the project repository, not in the npm package.

## License

MIT. See [LICENSE](./LICENSE).
