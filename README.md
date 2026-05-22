# bigquery_csv_uploader

A Google Colab notebook that loads a CSV file from Google Drive into a
[Google BigQuery](https://cloud.google.com/bigquery) table using pandas and a
service-account credential.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/the-farshad/bigquery_csv_uploader/blob/main/bq_csv_uploader.ipynb)

## How it works

The notebook (`bq_csv_uploader.ipynb`):

1. Mounts your Google Drive in Colab.
2. Reads a CSV from a Drive folder into a pandas DataFrame.
3. Authenticates with a BigQuery service account (`service_account.json`).
4. Writes the DataFrame to a BigQuery table with `DataFrame.to_gbq`.

## Setup

Place the following in the Drive folder referenced by `files_path`
(default `/content/drive/MyDrive/bq/`):

- the CSV file you want to upload (default `products.csv`)
- a BigQuery service-account key named `service_account.json`

Then adjust `name` and `table_id` in the notebook to match your file and
destination dataset/table, and run the cells in order.

> **Note:** keep your `service_account.json` private — never commit it to the
> repository.

## License

Released under the [GPL-3.0](LICENSE) license.
