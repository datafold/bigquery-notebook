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

Add the following cell to the notebook to install the SDK from your local environment.

```python
# FOR LOCAL DEVELOPMENT, NOT NEEDED ON COLAB/DATABRICKS
import os
import pathlib
from dotenv import load_dotenv
load_dotenv()

LOCAL_DMA_SDK_PATH = os.getenv('LOCAL_DMA_SDK_PATH')
if LOCAL_DMA_SDK_PATH and pathlib.Path(LOCAL_DMA_SDK_PATH).exists():
    print(f"Installing dma-sdk from {LOCAL_DMA_SDK_PATH}")
    %pip install --editable "{LOCAL_DMA_SDK_PATH}"
    
    # Restart to make dependencies available
    import IPython
    app = IPython.Application.instance()
    app.kernel.do_shutdown(True)
```
