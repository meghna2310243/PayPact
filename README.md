# 💸 PayPact

# PayPact — Execution Instructions

PayPact is a full-stack bill-splitting and payment tracking web application.  
**Backend:** Django REST Framework + SQLite  
**Frontend:** React (Vite) + Tailwind CSS

---

## Prerequisites

| Tool | Version |
|------|---------|
| Python | 3.10+ |
| Node.js | 18+ |
| npm | 9+ |

---

## 1. Clone the Repository

```bash
git clone <repository-url>
cd PayPact
```

---

## 2. Backend Setup (Django)

### 2a. Create & Activate Virtual Environment

```bash
# From the project root
python3 -m venv venv
source venv/bin/activate        # macOS / Linux
# venv\Scripts\activate         # Windows
```

### 2b. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2c. Apply Migrations

```bash
cd backend
python manage.py migrate
```

### 2d. (Optional) Create a Superuser

```bash
python manage.py createsuperuser
```

### 2e. Run the Django Development Server

```bash
python manage.py runserver
```

The backend will be available at **http://127.0.0.1:8000/**  
Admin panel: **http://127.0.0.1:8000/admin/**

---

## 3. Frontend Setup (React + Vite)

Open a **new terminal tab/window**.

```bash
# From the project root
cd frontend
npm install
npm run dev
```

The frontend will be available at **http://localhost:5173/**

---

## 4. Running Both Servers Together

You need **two terminals** running simultaneously:

| Terminal | Directory | Command |
|----------|-----------|---------|
| Terminal 1 | `PayPact/backend/` | `python manage.py runserver` |
| Terminal 2 | `PayPact/frontend/` | `npm run dev` |

Open your browser and navigate to **http://localhost:5173/** to use the app.

---

## 5. Environment Notes

- The backend uses **SQLite** (`backend/db.sqlite3`) — no separate database installation required.
- CORS is enabled for all origins in development mode (`CORS_ALLOW_ALL_ORIGINS = True`).
- Razorpay test credentials are pre-configured in `backend/backend/settings.py`.
- JWT authentication is used for all protected API endpoints.
- `DEBUG = True` — do **not** use these settings in production.

---

## 6. Project Structure

```
PayPact/
├── backend/                # Django project
│   ├── backend/            # Project settings, URLs, WSGI/ASGI
│   ├── core/               # Main app (models, views, serializers)
│   ├── manage.py
│   └── db.sqlite3
├── frontend/               # React + Vite app
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── vite.config.js
├── requirements.txt        # Python dependencies
└── README.md
```

---

## 7. Useful Commands

```bash
# Run backend tests
cd backend && python manage.py test

# Lint frontend
cd frontend && npm run lint

# Build frontend for production
cd frontend && npm run build

# Open Django shell
cd backend && python manage.py shell
```


## 👨‍💻 Authors:
Rahul Malaikani, Meghna Manimaran
