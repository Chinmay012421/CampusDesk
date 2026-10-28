# 🏫 SchoolFix — Student Voice Portal

**SchoolFix** is a student voice portal designed to help students report school-related issues and communicate their concerns through a dedicated online platform.

Built with **Python, Flask, and Supabase**, SchoolFix provides a role-based system for students, administrators, and main administrators to manage reports and support a safer, more supportive school environment.

---

## ✨ Features

### 👨‍🎓 Student Portal
- Create a student account and log in securely.
- Submit reports about school-related issues.
- Submit anonymous reports.
- View your own reports.
- Track report statuses.
- Communicate about reports through the reporting system.
- Change your account password.
- Access useful student resources from the dashboard.

### 🛡️ Administrator Dashboard
- View reports assigned to the logged-in administrator.
- Manage assigned reports.
- Update report statuses.
- Add administrative notes.
- Review student concerns.

### 👑 Main Administrator Panel
- Access administrative management features.
- Manage users and administrator applications.
- Review and manage reports across the platform.
- Access analytics.
- View security monitoring information.

### 🔐 Security
- Password hashing using Werkzeug.
- Session-based authentication.
- Role-based access control.
- Protected routes for students and administrators.
- Security event logging for login successes, failed login attempts, and logout events.
- Main administrator credentials configured through environment variables.

### 📱 Responsive Interface
- Mobile-friendly layout improvements.
- Responsive navigation and page layouts.
- Forms and dashboard cards designed to work across screen sizes.

---

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| Python | Backend programming |
| Flask | Web application framework |
| Supabase | Database and backend services |
| PostgreSQL | Database used by Supabase |
| Werkzeug | Password hashing and security utilities |
| HTML | Page structure |
| CSS | Styling and responsive layouts |
| Gunicorn | Production application server |
| Render | Web application hosting |
| GitHub | Source code management |

---

## 📁 Project Structure

The main project files include:

```text
CampusDesk/
├── app.py
├── database.py
├── requirements.txt
├── render.yaml
├── templates/
│   ├── base.html
│   ├── home.html
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   ├── reports.html
│   └── ...
└── static/
    ├── style.css
    ├── bg_image.png
    └── uploads/
```

*Note: The exact files and folders may vary depending on your current repository version.*

---

## ⚙️ Running the Project Locally

### 1. Install Python

Install a compatible Python version. The included Render configuration specifies Python `3.13.5`.

### 2. Clone the Repository

```bash
git clone https://github.com/Chinmay012421/CampusDesk.git
cd CampusDesk
```

### 3. Create a Virtual Environment

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure Environment Variables

Before starting the application, configure the following environment variables.

| Variable | Purpose |
|---|---|
| `FLASK_SECRET_KEY` | Secret key used to sign Flask sessions |
| `SUPABASE_URL` | Your Supabase project URL |
| `SUPABASE_SERVICE_KEY` | Supabase service-role key used by the backend |
| `MAIN_ADMIN_USERNAME` | Username for the first configured main administrator |
| `MAIN_ADMIN_PASSWORD` | Password for the first configured main administrator |

The application also supports additional main administrator accounts through:

- `MAIN_ADMIN_2_USERNAME`
- `MAIN_ADMIN_2_PASSWORD`
- `MAIN_ADMIN_3_USERNAME`
- `MAIN_ADMIN_3_PASSWORD`
- `MAIN_ADMIN_4_USERNAME`
- `MAIN_ADMIN_4_PASSWORD`
- `MAIN_ADMIN_5_USERNAME`
- `MAIN_ADMIN_5_PASSWORD`

Set only the accounts you need.

**Important:** Keep all secret keys and administrator passwords private. Never commit them to GitHub.

### 6. Set Up Supabase

1. Create a Supabase project.
2. Configure the database tables and columns required by `database.py`.
3. Obtain your project URL and backend service-role key.
4. Set `SUPABASE_URL` and `SUPABASE_SERVICE_KEY` in your local environment.

The database schema must match the operations expected by the application.

### 7. Start the Application

Run:

```bash
python app.py
```

If your application does not start this way, check whether `app.py` defines a local development entry point.

---

## ☁️ Deployment on Render

SchoolFix includes a `render.yaml` configuration for deployment on Render.

### Deployment Steps

1. Push your project to GitHub.
2. Sign in to Render.
3. Create a Web Service connected to your repository.
4. Configure the required environment variables.
5. Deploy the application.

The configured build command is:

```bash
pip install -r requirements.txt
```

The configured start command is:

```bash
gunicorn --bind 0.0.0.0:$PORT app:app
```

### Required Render Environment Variables

Configure these in your Render service's environment settings:

```text
FLASK_SECRET_KEY
SUPABASE_URL
SUPABASE_SERVICE_KEY
MAIN_ADMIN_USERNAME
MAIN_ADMIN_PASSWORD
```

Add any additional main administrator variables you use.

Do not paste real credentials into your README or public repository.

---

## 🔑 Main Administrator Setup

Main administrator accounts are configured using environment variables.

During database initialization, the application checks whether each configured username already exists. It creates a main administrator account when the configured username does not already exist.

Existing accounts are not automatically overwritten.

Keep main administrator credentials secure and use strong, unique passwords.

---

## 🔒 Privacy and Security

SchoolFix is intended to provide a controlled environment for submitting and managing student concerns.

- Students should only be able to access their own reports.
- Administrators should access reports assigned to them.
- Main administrators have broader administrative access.
- Passwords are stored using password hashing rather than being stored as plain text.
- Backend service credentials must remain private.
- Security logs may contain usernames, IP addresses, timestamps, and security events.

Always verify authorization rules, database permissions, and file-upload handling before using the application with real student information.

---

## 🚀 Project Goals

SchoolFix aims to:

- Give students a convenient way to communicate school-related concerns.
- Make report management more organized.
- Support responsible communication between students and administrators.
- Provide role-based access to sensitive reports.
- Improve accessibility across mobile and desktop devices.

---

## 👨‍💻 Development

Contributions, bug reports, and suggestions are welcome.

When modifying the project:

1. Test changes locally.
2. Verify that role-based access still works.
3. Check the interface on both mobile and desktop screens.
4. Keep credentials and sensitive student information out of source control.
5. Test deployment after pushing changes to GitHub.

---

## 📄 License

No license has been specified in this README. Add an appropriate license file if you intend to permit others to reuse or distribute the project.

---

**SchoolFix — A safer way to make your school heard.**
