# 🏥 MediCore HMS — Hospital Management System

A web-based Hospital Management System built with **Flask**, **MySQL** and **HTML/CSS/JavaScript**. It helps manage day-to-day hospital operations from a single dashboard.

## ✨ Features

- **Dashboard** – quick overview of today's appointments and key hospital stats
- **Patients** – add, view and manage patient records
- **Doctors & Staff** – manage doctors, specializations and staff details
- **Appointments** – book appointments, filter by status (Scheduled / Completed / Cancelled), and update them
- **Billing & Payments** – create and track patient bills
- **Pharmacy** – manage medicines and monitor low stock
- **Wards & Rooms** – track hospital wards and room availability

## 🛠️ Tech Stack

| Layer     | Technology                     |
|-----------|--------------------------------|
| Backend   | Python, Flask, Flask-CORS      |
| Database  | MySQL (PyMySQL)                |
| Frontend  | HTML, CSS, JavaScript          |

## 📁 Project Structure

```
hospital_project/
├── app.py                    # Flask backend (REST API)
├── hospital_management.html  # Frontend (UI)
├── hospital_schema.sql       # MySQL database schema
├── requirements.txt          # Python dependencies
└── README.md
```

## 🚀 Getting Started

### 1. Prerequisites

- Python 3.8+
- MySQL Server
- Git (optional)

### 2. Clone the repository

```bash
git clone https://github.com/MohdPaikerAbbas/hospital-management-system.git
cd hospital-management-system
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up the database

Open MySQL and run the schema file:

```bash
mysql -u root -p < hospital_schema.sql
```

This creates the `hospital_db` database and its tables.

### 5. Configure the database connection

In `app.py`, update `DB_CONFIG` with your own MySQL details:

```python
DB_CONFIG = {
    "host": "127.0.0.1",
    "user": "root",
    "password": "YOUR_MYSQL_PASSWORD",
    "database": "hospital_db",
    ...
}
```

### 6. Run the application

```bash
python app.py
```

Then open your browser and go to:

```
http://127.0.0.1:5000/
```

## 🔌 API Endpoints (examples)

| Method | Endpoint                  | Description               |
|--------|---------------------------|---------------------------|
| GET    | `/api/appointments`       | List appointments (filter by `date`, `status`) |
| POST   | `/api/appointments`       | Book a new appointment    |
| PUT    | `/api/appointments/<id>`  | Update status / notes     |
| GET    | `/api/bills`              | List bills                |
| GET    | `/api/medicines`          | List medicines (`low_stock=true` supported) |

## 🐛 Troubleshooting

- **"Cannot connect to Flask backend"** – make sure `python app.py` is running on port 5000.
- **Database connection error** – check your MySQL username, password and that MySQL is running.
- **`TypeError: Object of type timedelta is not JSON serializable`** – already handled in `app.py` with a custom JSON provider.

## 🔮 Future Improvements

- User login and role-based access (admin, doctor, receptionist)
- Reports and analytics
- Patient medical history and prescriptions
- Email/SMS appointment reminders

## 📄 License

This project is for learning and educational purposes.

---

⭐ If you found this project useful, consider giving it a star!
