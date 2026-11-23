# RAG-with-vector

## Start im Dev Container

1. Docker Desktop starten und in VS Code die Extension **Dev Containers** installieren.
2. Dieses Repository in VS Code öffnen und über die Command Palette
   **Dev Containers: Reopen in Container** ausführen.
3. Warten, bis die Packages aus `requirements.txt` installiert sind.
4. In `.env` im Projektverzeichnis `OPENAI_API_KEY` setzen. Optional können
   `OPENAI_MODEL` und `EMBEDDING_MODEL` gesetzt werden. Die Datei bleibt lokal
   und wird vom Notebook geladen.
5. `ml2_exercise2.ipynb` öffnen und über **Select Kernel → Python Environments**
   den Container-Interpreter `/usr/local/bin/python` (Python 3.12) wählen.
6. Die Aufgaben im Notebook bearbeiten und die Zellen der Reihe nach ausführen.

Im Container ist keine separate `.venv` nötig. Eine bestehende macOS-`.venv`
sollte nicht als Kernel im Linux-Container verwendet werden.
Die PDFs in `data` stehen über das eingebundene Projektverzeichnis zur Verfügung.

Optional lässt sich JupyterLab im Container-Terminal starten:

```sh
python -m jupyterlab --ip=0.0.0.0 --port=8888 --no-browser
```

Port 8888 wird an den Host weitergeleitet. Den im Terminal ausgegebenen Link
mit Token im Browser öffnen.

Nach Änderungen an `.devcontainer/devcontainer.json` **Dev Containers: Rebuild Container**
ausführen. Bei Änderungen an `requirements.txt` genügt im Container-Terminal
`python -m pip install -r requirements.txt`.
