# 🔗 URL Encurter

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.12+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)

A lightweight and fast URL shortener service built with **Python**, **FastAPI**, and **PostgreSQL**. No front-end framework needed — just a clean API.

## 📐 Architecture

<img width="828" height="387" alt="Architecture diagram" src="https://github.com/user-attachments/assets/fd9be0f2-5599-4431-9fc3-057afd139361" />

## ✨ Features

- 🚀 **Fast** — Powered by FastAPI with async support
- 🗄️ **Persistent storage** — URLs stored in PostgreSQL
- 🔑 **Short link generation** — Unique, compact short codes
- 📊 **Click tracking** — Track how many times a link is accessed *(planned)*
- 🧹 **Link expiration** — Auto-expire links after a configurable TTL *(planned)*

## 🛠️ Tech Stack

| Layer       | Technology                         |
|-------------|------------------------------------|
| Language    | Python 3.12+                       |
| Framework   | FastAPI                            |
| Database    | PostgreSQL                         |
| CI/CD       | GitHub Actions (reusable workflow) |

## 🚀 Getting Started

### Prerequisites

- [Python 3.12+](https://www.python.org/downloads/)
- [PostgreSQL](https://www.postgresql.org/download/)
- [pip](https://pip.pypa.io/) or [uv](https://github.com/astral-sh/uv)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/Gaguinhos/url-encurter.git
   cd url-encurter
   ```

2. **Create a virtual environment**

   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux / macOS
   # .venv\Scripts\activate   # Windows
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**

   Create a `.env` file in the project root:

   ```env
   DATABASE_URL=postgresql+asyncpg://user:password@localhost:5432/url_encurter
   ```

5. **Run the application**

   ```bash
   uvicorn app.main:app --reload
   ```

   The API will be available at `http://localhost:8000`.  
   Interactive docs at `http://localhost:8000/docs`.

## 📡 API Endpoints

> ⚠️ **Work in progress** — endpoints will be documented as they are implemented.

| Method   | Endpoint          | Description                    |
|----------|-------------------|--------------------------------|
| `POST`   | `/shorten`        | Create a new short URL         |
| `GET`    | `/{short_code}`   | Redirect to the original URL   |
| `GET`    | `/stats/{short_code}` | Get click stats for a link |
| `DELETE` | `/{short_code}`   | Delete a short URL             |

## 📁 Project Structure

```
url-encurter/
├── .github/
│   └── workflows/
│       └── ci.yml          # CI pipeline (reusable workflow)
├── .gitignore
├── LICENSE
└── README.md
```

> The source code structure will grow as the project develops. Planned layout:
>
> ```
> url-encurter/
> ├── app/
> │   ├── main.py            # FastAPI application entry point
> │   ├── models/            # SQLAlchemy / database models
> │   ├── routes/            # API route handlers
> │   ├── schemas/           # Pydantic request/response schemas
> │   ├── services/          # Business logic
> │   └── config.py          # Settings & environment config
> ├── tests/                 # Test suite
> ├── requirements.txt
> └── ...
> ```

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'feat: add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

Please follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/Gaguinhos">Gaguinhos</a>
</p>
