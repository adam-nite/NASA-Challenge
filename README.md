# Trend Detective

2026 NASA Space Apps Challenge. Challenge: "Be an Earth System Trend Detective".

A web page that retrieves monthly NASA data (1981-2025) for any location, removes the seasonal cycle, estimates the
rate of change (Sen's slope and a least-squares fit with a 95% confidence interval) and tests significance
(Mann-Kendall test and t-test). A regional map tests a grid of points and shows where the same variable
increases in one place and decreases in another.

## Files
- `index.html`: the application (open this file)
- `plotly.min.js`: Plotly.js 2.35.2 (MIT licence), charts and map
- `world_50m.json`: Natural Earth base map (public domain), supplied with Plotly
Keep all three files in the same folder.

## Run
Open `index.html` in a browser. An internet connection is needed to reach NASA POWER. No install.

## Data
NASA POWER monthly API (https://power.larc.nasa.gov), NASA Langley Research Center, 1981-2025.
Meteorological variables come from MERRA-2 (NASA GMAO); solar radiation and cloud variables from CERES.
Other NASA data (MODIS, OMI, AIRS, GPM, GLDAS) can be loaded as CSV files downloaded from NASA Giovanni.

## Method
Monthly values, then subtract each calendar month's long-term mean, then average complete years, then Sen's slope
and ordinary least squares, then Mann-Kendall test and t-test. A trend is called significant only when both tests
give p < 0.05. The statistical routines were checked against SciPy (linregress, kendalltau, theilslopes).

## AI disclosure
The code, interface text and documentation were generated with the assistance of Claude (Anthropic), an AI (SI) tool,
and then tested and reviewed by the team. The variable suggestions in the app are rule-based, not generated at run time.
