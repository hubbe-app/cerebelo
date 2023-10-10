# Welcome to the Cerebelo API

This Flask server allows you to manage, process, and query a collection of documents to retrieve relevant answers based on user input.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Setup](#setup)
- [Running the Server](#running-the-server)
- [API Endpoints](#api-endpoints)
- [License](#license)

## Features

1. **Manage Source Documents**: Upload, save, and clear out the collection of source documents for the QA system.
2. **Document Ingestion**: Process and index the uploaded documents, making them ready for retrieval tasks.
3. **Prompt-based Retrieval**: Retrieve relevant answers and source documents based on a user's prompt.

## Requirements

- Python 3.11
- Flask
- Torch
- Other dependencies as mentioned in `requirements.txt`.

## Setup

1. Clone the repository:
```bash
git clone https://github.com/hubbe-app/cerebelo
```

2. Navigate to the project directory:
```bash
cd cerebelo
```

3. Install the required packages:
```bash
pip install -r requirements.txt
```

## Running the Server

To run the Flask server:

```bash
python run_api.py
```

By default, the server will run on port 5110 and will be accessible at `http://0.0.0.0:5110/`.

API Endpoints

1.  Delete Source Documents
    -   Endpoint: `/api/delete_source`
    -   Method: `GET`
    -   Description: Deletes all documents in the `SOURCE_DOCUMENTS` directory and recreates the directory.

2.  Save Documents
    -   Endpoint: `/api/save_document`
    -   Methods: `GET`, `POST`
    -   Description: Save the document provided in the request to the `SOURCE_DOCUMENTS` directory.

3.  Run Ingest
    -   Endpoint: `/api/run_ingest`
    -   Method: `GET`
    -   Description: Execute the `ingest.py` script to process the documents in `SOURCE_DOCUMENTS`, generate embeddings, and update the retriever.

4.  Prompt Retrieval
    -   Endpoint: `/api/prompt_route`
    -   Methods: `GET`, `POST`
    -   Description: Given a user's prompt, this returns the relevant answer from the available embeddings and the source documents associated with the answer.

## Reference projects

https://github.com/PromtEngineer/localGPT

## License
```
MIT License

Copyright (c) 2023 Hubbe

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
