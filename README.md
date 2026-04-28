# Active Workers vs. Retirees — U.S. Public Pensions (2001–2024)

An animated **slope chart** visualizing the changing ratio of active workers to retirees in America's public pension system. Inspired by a [Visual Capitalist / Voronoi infographic](https://www.visualcapitalist.com/) using data from Equable Institute.

Each line represents a single year. The **left end** of the line is the number of active workers (in millions); the **right end** is the number of retirees (in millions). Early years trend teal; recent years trend orange. Lines that slope *upward* mark years where retirees outnumber active workers — the trend that has defined U.S. public pensions since 2012.

## Live demo

Once GitHub Pages is enabled for this repo, the chart is served at:

**https://acotgreave.github.io/active-workers-vs-retirees/**

## Features

- **D3.js slope chart** with two millions-scale axes and a continuous teal-to-orange color ramp encoding year.
- **Horizontal crossover reference line** at ~13.25M — the threshold where workers and retirees reached parity in 2012.
- **Animate toggle** — switch on to reveal one year at a time (cumulative), so the slope flip is visible in sequence. Switch off for the complete chart.
- **Replay** button to re-run the animation.
- **Blog-width** (740px) layout with editorial typography (Georgia display face, Inter body).
- Self-contained single `index.html` — no build step, no bundler. D3 is loaded from a CDN.

## Data

| Year | Active Workers (M) | Retirees (M) |
|------|-------------------:|-------------:|
| 2001 | 12.7 | 7.6  |
| 2002 | 12.9 | 8.0  |
| 2003 | 13.0 | 8.7  |
| 2004 | 12.9 | 9.3  |
| 2005 | 13.2 | 9.9  |
| 2006 | 13.2 | 10.6 |
| 2007 | 13.5 | 10.9 |
| 2008 | 13.7 | 11.3 |
| 2009 | 13.7 | 11.8 |
| 2010 | 13.7 | 12.3 |
| 2011 | 13.4 | 12.7 |
| **2012** | **13.2** | **13.3** |
| 2013 | 13.0 | 13.9 |
| 2014 | 13.1 | 14.3 |
| 2015 | 13.3 | 14.7 |
| 2016 | 13.3 | 15.3 |
| 2017 | 13.6 | 15.5 |
| 2018 | 13.5 | 16.3 |
| 2019 | 13.2 | 16.6 |
| 2020 | 13.5 | 16.6 |
| 2021 | 13.1 | 17.6 |
| 2022 | 13.4 | 18.8 |
| 2023 | 13.7 | 19.5 |
| 2024 | 14.5 | 18.8 |

**Source:** Equable Institute analysis of public-plan valuation reports and Annual Comprehensive Financial Reports (ACFRs), republished by Visual Capitalist / Voronoi. Values are estimates.

## How it works

The chart is a classic **slope chart**: two vertical value axes (left = active workers, right = retirees), with one line per year connecting that year's two values. The line's slope reveals the balance — downward slopes mean workers outnumber retirees, upward slopes mean the reverse.

Year is encoded as a color via a perceptually smooth three-stop ramp (teal → warm cream → orange) built with `d3.interpolateRgbBasis`, which echoes the original Voronoi palette while remaining readable as a continuous sequence.

The horizontal reference line at ~13.25M marks the 2012 crossover — the point at which retirees first equaled workers. Every line whose right endpoint sits above this level represents a year where retirees outnumber workers.

## Running locally

Clone the repo and open `index.html` directly in a browser:

```bash
git clone https://github.com/acotgreave/active-workers-vs-retirees.git
cd active-workers-vs-retirees
# macOS
open index.html
# Windows
start index.html
# Or serve with any static server:
python3 -m http.server 8000
# then open http://localhost:8000
```

No build step, no dependencies beyond D3 v7 (loaded from jsDelivr).

## Project structure

```
active-workers-vs-retirees/
├── index.html     # single-file chart (HTML + CSS + D3 JS)
└── README.md
```

## License

MIT. Data used under fair use for non-commercial analysis; credit to Equable Institute and Visual Capitalist.
