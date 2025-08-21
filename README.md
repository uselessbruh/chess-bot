
<p align="center">
   <img src="https://img.shields.io/badge/Chess%20Bot-Stockfish%20%2B%20Flask-blueviolet?style=for-the-badge&logo=python&logoColor=white" alt="Chess Bot"/>
</p>

# ♟️ Chess Bot

> <span style="color:#4CAF50"><b>Play chess against Stockfish AI in your browser!</b></span>

A feature-rich Flask backend for chess, powered by the Stockfish engine and `python-chess`. Easily integrate with any frontend for a smart, interactive chess experience.

---

## ✨ Features

- ♟️ **Play chess against Stockfish AI**
- 🎚️ **Adjustable AI difficulty** (Stockfish depth)
- ✅ **Move validation** and legal move generation
- 🕰️ **Game state & move history tracking**
- 🔗 **RESTful API** for easy frontend integration
- 📝 **PGN export** for your games

---

## 🛠️ Requirements

- Python 3.7+
- Stockfish binary (`stockfish.exe` in `stockfish/`)
- See [`requirements.txt`](./requirements.txt) for Python dependencies

---

## 🚀 Installation

```bash
# 1. Clone this repository
git clone https://github.com/uselessbruh/chess-bot.git
cd chess-bot

# 2. Install Python dependencies
pip install -r requirements.txt

# 3. Ensure Stockfish binary is present
# (stockfish/stockfish.exe by default)
```

---

## ▶️ Running the Backend

```bash
python app.py
```

The server will start at: [http://0.0.0.0:5000/](http://0.0.0.0:5000/)

---



## 🗂️ Project Structure

```text
chess-bot/
├── app.py              # Flask backend
├── requirements.txt    # Python dependencies
├── templates/
│   └── index.html      # (Frontend template, if present)
├── stockfish/
│   ├── stockfish.exe   # Stockfish engine binary
│   └── ...             # (Source, docs, not needed for running)
└── ...
```

---

## ⚠️ Limitations

> **:warning: This backend is NOT scalable for multiple users playing at the same time.**

- The backend uses a single global game instance, so all users share the same board and engine.
- For production or multi-user support, refactor to manage separate game sessions per user (using sessions, authentication, or unique game IDs).

---

## 🛡️ Error Handling & Troubleshooting

- If Stockfish is not found, ensure `stockfish.exe` is in the correct folder or update the path in `app.py`.
- Invalid moves return `{ "success": false, "error": "Invalid move" }`.
- Engine errors or missing dependencies will return a 500 error with a message.
- For CORS issues, ensure `flask-cors` is installed and enabled.

---

## 🌐 Frontend Integration

- Use any frontend (React, Vue, plain HTML/JS) to interact with the API.
- Example: Use [chessboard.js](https://chessboardjs.com/) or [react-chessboard](https://github.com/Clariity/react-chessboard) for the board UI.
- Send moves as UCI strings (e.g., `e2e4`) to the backend.

---

## 🏗️ Customization & Extending

- Add user authentication for multi-user support.
- Store games in a database for persistence.
- Add more endpoints (e.g., analysis, hints, puzzles).
- Deploy with Gunicorn + Nginx for production.

---

## 🚢 Deployment

For production:

```bash
pip install gunicorn
gunicorn -w 4 app:app
```

Use a process manager (e.g., Supervisor) and a reverse proxy (e.g., Nginx) for best results.

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---


## 📄 License

This project is licensed under the **MIT License**. See the [`LICENSE`](./LICENSE) file for details.

---

## 🙏 Credits

- [Stockfish](https://stockfishchess.org/)
- [python-chess](https://python-chess.readthedocs.io/)

<p align="center">
   <img src="https://img.shields.io/badge/Happy%20Playing!-chess-green?style=for-the-badge&logo=chess&logoColor=white" alt="Happy Playing!"/>
</p>
