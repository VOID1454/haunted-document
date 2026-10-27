THE HAUNTED DOCUMENT — QUICK START (WINDOWS)

1. Extract all files from the ZIP into a folder.
2. Install Python 3.10 or newer from https://www.python.org/downloads/ (select Add Python to PATH). Python and dependency installation require internet.
3. Open Ollama. In Command Prompt run: ollama pull llama3.2
   If you already have a model, use its exact name in the app instead. Downloading a model requires internet and disk space.
4. Double-click Start_Haunted_Document.bat. The first launch installs dependencies, which requires internet. Wait for the app to open in your browser.
5. Upload a text-based PDF and ask a question. Check the page references against the original PDF.

After setup, the app and a locally installed model can work without internet. Leave Ollama running. This app processes the PDF locally and sends excerpts and questions to Ollama at 127.0.0.1; do not configure Ollama to forward requests to a remote model if you need local processing. PDFs and conversations are held in app memory, not saved by this app. Stop the app by closing its terminal window.

LIMITATIONS
- Scanned/image-only PDFs need OCR first. Password-protected PDFs must be unlocked first.
- Search uses keyword matching, so relevant passages may be missed; the AI can make mistakes or cite pages incorrectly. Review the original document.
- Large PDFs, complex layouts, charts, and tables may not extract accurately. Answers use up to six selected excerpts, not necessarily the whole document.
- This is a prototype; do not rely on answers for consequential decisions without checking the source.

MAC/LINUX: Install Python and Ollama, then run: python3 -m venv .venv; source .venv/bin/activate; pip install -r requirements.txt; streamlit run app.py --server.address 127.0.0.1
