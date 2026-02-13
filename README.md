## Local setup (uv)

```bash
uv sync
```

## Jupyter notebooks

`ipykernel` is included in this project dependencies, so after syncing you can register this environment as a notebook kernel on macOS and Windows:

```bash
uv run python -m ipykernel install --user --name gsheets2api --display-name "Python (gsheets2api)"
```

## Notebook.link

- Repo in JupyterLab:
[Open in Notebook.link (Lab)](https://notebook.link/github/SustainableUrbanSystemsLab/GSheets2API/tree/main/lab/)


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
