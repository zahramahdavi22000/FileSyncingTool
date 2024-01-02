# File Syncing Tool
This repository contains a simple Python-based file synchronization tool. The tool comprises two components: a client-side script and a server implemented using FastAPI.

## Purpose
The purpose of this tool is to synchronize files between a client and a server. The client script detects changes in a specified directory and uploads modified files to the server. The server stores the files and provides file hash verification.

## Usage

### Client-side Script

The client-side script (`client_sync.py`) continuously monitors changes in a specified directory (`target` by default). It compares local file hashes with those stored on the server (`http://127.0.0.1:8000` by default) and uploads any modified files to the server.

To use the client-side script:

1. Modify the configuration parameters in the script as needed (`CLIENT_PATH`, `SERVER_URL`, `TOKEN`, `CHECK_INTERVAL`).
2. Run the script using Python 3:
    ```
    python client_sync.py
    ```

### Server-side Script

The server-side script (`server.py`) is implemented using FastAPI and handles two endpoints: one for retrieving file hashes and another for uploading files.

To use the server-side script:

1. Run the server script using python 3:
    ```
    python server.py
    ```

### API Endpoints

- **GET `/get_file_hash`**: Retrieves the hash of a specified file from the server.
- **POST `/upload_file`**: Uploads a file to the server.

### Configuration

Adjust the following parameters in both scripts as needed:

- For the client-side script: `CLIENT_PATH`, `SERVER_URL`, `TOKEN`, `CHECK_INTERVAL`.
- For the server-side script: `SERVER_PATH`, `TOKEN`.

## Requirements

- Python 3
- Required Python libraries: `requests`, `hashlib`, `time` (for client-side); `uvicorn`, `fastapi`, `os`, `hashlib` (for server-side)