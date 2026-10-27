# 👻 The Haunted Document

A ghostly librarian that answers questions about your PDFs using an Ollama model running on your computer. Built for the Hacktoberfest Open-Source AI Challenge: Ghost in the Machine.

## Features

- Upload a text-based PDF and ask questions about it.
- Extract text page by page, then use keyword search to find relevant passages.
- Generate an answer with a local Ollama model; inspect the passages sent to the model.
- Use a dark, ghost-themed chat interface.

## Requirements

- Python 3.10 or newer
- [Ollama](https://ollama.com/) running locally
- A locally installed model, such as `llama3.2`
- Internet access for initial dependency installation and model download

## Windows: quick start

1. Download the repository using **Code → Download ZIP**, then extract it.
2. Install Python, selecting **Add Python to PATH** during installation.
3. Open Ollama, then open Command Prompt and run:

   ```bash
   ollama pull llama3.2
   ```

4. Double-click `Start_Haunted_Document.bat`. The first run installs Python dependencies and opens the app in your browser.
5. Upload a PDF and ask a question. To use a different locally installed Ollama model, enter its exact name in the sidebar.

## Manual setup

Create and activate a virtual environment, then run:

```bash
pip install -r requirements.txt
streamlit run app.py --server.address 127.0.0.1
```

For example, create a virtual environment with `python -m venv .venv`; activate it with `.venv\Scripts\activate` on Windows or `source .venv/bin/activate` on macOS/Linux. Keep Ollama running.

## How it works

1. `pypdf` extracts text from each PDF page.
2. The app splits the text into overlapping passages and ranks them using keyword matches.
3. Up to six selected passages and the question are sent to Ollama at `127.0.0.1:11434`.
4. The model is instructed to answer from the passages and cite page numbers. The selected passages can be inspected in the interface.

## Privacy and limitations

After setup, the app can run offline with a locally installed model. The app processes the PDF locally and sends selected passages to the local Ollama endpoint. It does not save PDFs or conversations itself. Ensure your Ollama configuration uses a local model if local processing is required.

The app is a prototype. Image-only PDFs need OCR first; password-protected PDFs must be unlocked. Complex tables and layouts may extract poorly. Keyword search may miss relevant content, and model answers or page citations may be inaccurate or absent. Verify answers against the PDF, especially for important decisions.
