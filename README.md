# Weather time series project

This workspace contains:

- `have_fun.xlsx` - the original Excel workbook with hidden sheets and mixed-quality weather data.
- `timeseries_weather_pipeline.ipynb` - the notebook with parsing, cleaning, EDA, feature engineering, and forecasting scaffolding.
- `cleaned_weather.csv` / `weather_panel_canonical.csv` - cleaned tabular outputs.

## What the notebook does

1. Opens the workbook with `openpyxl` and lists all sheets, including hidden ones.
2. Selects only sheets that contain a `ds` column.
3. Decodes the `city` field from the broken cp1251/latin-1 text representation.
4. Canonicalizes city names such as `Мосва -> Москва`, `Геленджи -> Геленджик`, `Сочи` variants, and similar typos.
5. Converts timestamps and numeric columns to proper types.
6. Rebuilds an hourly panel per city, fills gaps, clips extreme outliers, and saves the result to `weather_panel_canonical.csv`.
7. Runs EDA helpers, stationarity checks, seasonal decomposition, spectral analysis, feature engineering, and model-training scaffolding.

## How to run

Open `timeseries_weather_pipeline.ipynb` in VS Code and select the Python kernel from `.venv`.

If needed, install dependencies from `requirements.txt`.
