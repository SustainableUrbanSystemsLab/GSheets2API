## Local setup (uv)

```bash
uv sync
```

Optional quick check:

```bash
uv run python -c "import requests, pandas; print('ok')"
```

If you want to work in the notebook:

```bash
uv run --with jupyter jupyter notebook GSX2JSON-tutorial.ipynb
```

## Notebook.link

This repository is configured for Notebook.link with `.nblink/environment.yml`.

- Repo in JupyterLab:
[Open in Notebook.link (Lab)](https://notebook.link/github/SustainableUrbanSystemsLab/GSheets2API/tree/main/lab/)
- Open `GSX2JSON-tutorial.ipynb` from the file browser after the workspace loads.
- Optional direct notebook link:
[Try opening `GSX2JSON-tutorial.ipynb` directly](https://notebook.link/github/SustainableUrbanSystemsLab/GSheets2API/tree/main/lab/?path=GSX2JSON-tutorial.ipynb)

If a direct `?path=...` link fails with `Failed to download file ... wrong format`, use the repo link above and open the notebook manually.

## Documentation

This API returns a given Google Sheet's rows as JSON data.

In order to use it:

1. The first row of your Google Sheet should be a header row  ([here's an example](https://docs.google.com/spreadsheets/d/1o5t26He2DzTweYeleXOGiDjlU4Jkx896f95VUHVgS8U/edit)).
1. Link sharing must be turned on so anyone with the link can _view_ the Google Sheet.

The format for this API is:

```
https://opensheet.elk.sh/spreadsheet_id/tab_name
```

For example:

```
https://opensheet.elk.sh/1o5t26He2DzTweYeleXOGiDjlU4Jkx896f95VUHVgS8U/Test+Sheet
```

You can also replace `tab_name` with the tab number (in the order that the tabs are arranged), if you don't know the name. For example, to get the first sheet:

```
https://opensheet.elk.sh/1o5t26He2DzTweYeleXOGiDjlU4Jkx896f95VUHVgS8U/1
```

_Take note that the first sheet in order is numbered `1`, not `0`._

Adding the `?raw=true` URL parameter returns the raw, unformatted data from the sheet. Without this parameter, Google Sheets formats numbers, dates, and other data types, but with `?raw=true`, you'll get the underlying values.
