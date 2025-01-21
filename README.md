# RedExt

## Overview
**RedExt** is a Chrome Extension and Flask-powered dashboard server designed for red teams. It captures keystrokes and displays them in a secure dashboard. The extension enables advanced analysis and monitoring for.

---

## Features

### Extension Features
1. **Keystroke Logging**
   - Tracks keystrokes across websites.
   - Associates captured keystrokes with the domain of the active tab.
   - Data is encrypted before being sent to the server.

2. **Encryption**
   - Utilizes XOR encryption for securing data.
   - Ensures that sensitive information is safely transmitted.

3. **Domain-Specific Data Handling**
   - Groups keystrokes by domain for better organization and analysis.
   - The data sent to the server in randome intervals that you can change.

### Dashboard Server Features
1. **Dark-Themed Interface**
   - A visually appealing.
   - Displays captured keystrokes in an organized manner.

2. **Client and Domain Management**
   - Lists all clients by unique IDs.
   - Displays domain-specific keystrokes for selected clients.

3. **Secure Storage**
   - Stores data in SQLite with tables for clients and keystrokes.

---

## Installation

### Extension Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```
2. Open Chrome and navigate to `chrome://extensions/`.
3. Enable "Developer mode".
4. Click "Load unpacked" and select the `extension` folder.
5. Ensure the extension is active.

### Dashboard Server Installation
1. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Initialize the database:
   ```bash
   flask db init
   flask db migrate -m "Initial migration."
   flask db upgrade
   ```
3. Run the server:
   ```bash
   flask run
   ```
4. Open the dashboard in your browser at `http://127.0.0.1:5000`.

---

## Usage

1. **Start the Flask server** to enable data collection.
2. **Load and activate the Chrome extension**.
3. Navigate to any website and use your keyboard. Keystrokes will be logged and associated with the current domain.
4. Open the Flask dashboard to view:
   - Clients.
   - Domains accessed by each client.
   - Keystrokes grouped by domain.

---

## File Structure

```
RedExt/
├── extension/
│   ├── background.js
│   ├── content.js
│   ├── manifest.json
│   └── static/
│       └── icons/
├── server/
│   ├── app.py
│   ├── config.py
│   ├── models.py
│   ├── migrations/
│   └── templates/
│       ├── base.html
│       ├── dashboard.html
│       ├── client_detail.html
│       ├── client_section_detail.html
│       └── host_detail.html
└── README.md
```

---

## Notes
- Ensure the server's encryption key matches the extension's encryption key.
- This project logs keystrokes and is intended for ethical use by authorized personnel only.
- Only keystroke logging is implemented. Other planned features (clipboard, screenshots, browser history, form data) are  currently functional in private repo, Maybe it will be published later.

---

## License
RedExt is licensed under the MIT License.
