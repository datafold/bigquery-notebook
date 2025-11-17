# BigQuery Notebook

Jupyter notebook for translating SQL queries from Snowflake to BigQuery using the Datafold DMA SDK.

## Setup

Install dependencies:

```bash
uv sync
```

## Running the Notebook

Start Jupyter Notebook:

```bash
uv run jupyter notebook
```

The server will start and provide a URL with an access token to open in your browser.

## Local Development

Create a `.env` file and set `LOCAL_DMA_SDK_PATH` pointing to the dma-sdk repo.
The notebook will then install using `pip install -e` which allows editing the SDK code.
The code gets automatically refreshed every time you run a cell.

Example `.env` file:
```
LOCAL_DMA_SDK_PATH=/path/to/dma-sdk
```
