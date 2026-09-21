# AixFinder
A local helper server for the **.aix Manager** Chrome extension.

<img width="1365" height="717" alt="image" src="https://github.com/user-attachments/assets/0d0f645b-ce7e-4c55-ac32-df72c0710ef9" />

This server provides file-system access that a Chrome extension cannot have on its own. It scans a folder you configure, returns the list of `.aix` extension files it contains, opens the native file explorer in the folder of a selected file, and stores your favorites list.

The companion Chrome extension is available on the Chrome Web Store: [https://chromewebstore.google.com/detail/edihhjpkefdiefdefeafidpkjlbncglf?utm_source=item-share-cp].

---

## What it does

The server listens only on `127.0.0.1:8765` (loopback address) and exposes a small HTTP API that the Chrome extension calls. It performs four tasks:

1. **Scan** a folder you configure and return the list of `.aix` files it contains.
2. **Open** the native file explorer in the folder of a selected `.aix` file.
3. **Store** and **retrieve** your favorites list.
4. **Broadcast** changes via Server-Sent Events (SSE) so multiple tabs stay in sync.

It does **not** send any data to remote servers. All communication stays on your machine.

---

## Requirements

- **Windows** (the precompiled `aixFinder.exe` is for Windows).
- No Python installation required if you use the `.exe`.

If you prefer to run it from source, you need:
- Python 3.8 or higher.

---

## Installation

### Option 1: Download the precompiled executable (recommended for most users)

1. Go to the [Releases](../../releases) page (or download `aixFinder.exe` directly from this repository).
2. Download `aixFinder.exe` to a folder of your choice (for example, `C:\AixFinder\`).
3. Double-click `aixFinder.exe` to start the server.
4. A console window will appear. Leave it running while you use the Chrome extension.

### Option 2: Run from source

1. Clone this repository:

   ```bash
   git clone https://github.com/Joejsanz/AixFinder.git
   cd AixFinder
