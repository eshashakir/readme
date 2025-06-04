# IseeDoc Backend

The IseeDoc Backend powers secure, scalable virtual healthcare solutions. Built with FastAPI, it supports robust user authentication, patient-doctor chat, medical report management, and is designed for easy integration with modern healthcare applications.


## Features

- 🚀 FastAPI-based REST API
- 🔒 JWT-based user authentication
- 🗄️ PostgreSQL integration
- 🗂️ CRUD operations for users & chat history
- 📜 Medical report management
- 🔄 Alembic for database migrations
- 💬 Patient-doctor chat module
- 🛡️ Extensible for AI-driven features and smart tools
- 📝 Logging and utilities for expansion

## Tech Stack

- **Backend:** FastAPI (Python 3.10+)
- **Database:** PostgreSQL
- **Auth:** JWT
- **Migrations:** Alembic
- **Containerization:** Docker (optional)
- **Other:** [add Redis, Celery, etc. here if needed]

## Getting Started

### Prerequisites

- Python 3.10+
- PostgreSQL
- Git

### 1. Clone the Repository

```bash
git clone <repository_url>
cd iseedoc-backend
````

### 2. Set Up Virtual Environment

```bash
python3.10 -m venv venv
source venv/bin/activate  # For Linux/Mac
venv\Scripts\activate     # For Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. PostgreSQL Setup

```sql
-- Log in to psql as postgres user
sudo -u postgres psql

-- Run:
CREATE DATABASE iseedoc;
CREATE USER iseedoc_user WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE iseedoc TO iseedoc_user;
```

### 5. Configure Environment Variables

Create a `.env` file in the root directory with:

```
DATABASE_URL=postgresql://iseedoc_user:yourpassword@localhost:5432/iseedoc
SECRET_KEY=your_secret_key
ALGORITHM=HS256
```

### 6. Run Database Migrations

```bash
alembic upgrade head
```

### 7. Start the Development Server

```bash
uvicorn main:app --reload
```

## Running with Docker (Optional)

> **Docker Compose file required (not included by default).**

1. Build & start containers:

```bash
docker-compose up --build
```

2. The app will be available at `http://localhost:8000`.

---

## Deployment

* **Production servers:** Use Gunicorn or Uvicorn workers behind Nginx.
* **Environment variables:** Store secrets securely (e.g., with Docker secrets, .env files, or a vault).
* **Database:** Use a managed PostgreSQL instance if available.
* **Scaling:** For async tasks, add Celery & Redis (see docs).

---

## API Documentation

Interactive docs auto-generated at runtime:

* **Swagger UI:** `http://localhost:8000/docs`
* **ReDoc:** `http://localhost:8000/redoc`

---

## Project Structure

```
iseedoc-backend/
├── alembic/
│   └── versions/
├── app/
│   ├── api/
│   ├── core/
│   ├── crud/
│   ├── db/
│   ├── models/
│   ├── schemas/
│   └── utils/
├── tests/
├── .env
├── .gitignore
├── alembic.ini
├── main.py
├── README.md
└── requirements.txt
```

---

## Testing

* Use Postman, cURL, or Swagger UI to test endpoints.
* Main routes:

  * `/signup` – Register a user
  * `/login` – Authenticate & receive JWT
  * `/profile` – Get protected user info
  * `/chat` – Patient-doctor chat (add docs if endpoint exists)
  * `/report` – Manage medical reports (add docs if endpoint exists)

---

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---

## License

Licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## Contact

* Email: \[[your.email@example.com](mailto:your.email@example.com)]
* GitHub: \[[https://github.com/yourusername](https://github.com/yourusername)]
* Project Lead: \[Your Name]

---

*Generated with ❤️ for modern healthcare applications.*

```

---

**How to use this:**
- Copy-paste to your README.md.
- Fill in placeholders (repository_url, yourpassword, your_secret_key, your email/name).
- Remove or add sections/features as your project evolves!

If you want me to insert actual API route samples, environment variable examples, or advanced deployment (like Nginx config), just let me know!
```
