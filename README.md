# 🚀 SprintHub

A Django-based web application containerized with Docker.

### 👨‍💻 Prerequisites

- Docker
- Docker Compose
- Python 3.x
- pip

### 📁 Project Structure
```bash
├── .env.dev
├── .gitignore
├── docker-compose.yml
├── Dockerfile
├── infra
│   └── dev
│       └── nginx
│           ├── default.conf
│           └── Dockerfile
├── manage.py
├── README.md
├── requirements.txt
├── sprinthub
│   ├── asgi.py
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── tracker
    ├── admin.py
    ├── apps.py
    ├── __init__.py
    ├── migrations
    │   └── __init__.py
    ├── models.py
    ├── tests.py
    └── views.py
```

### ⚙️ Setup Instructions

1. Copy the example environment file and adjust settings as needed:
```bash
cp .env.dev .env
```

2. Clone the repository:
```bash
git clone git@github.com:luca-fabbietti/sprinthub.git
cd sprinthub
```

3. Build and start the Docker containers:
```bash
docker-compose up --build -d
```

4. Apply database migrations:
```bash
docker-compose exec web python manage.py migrate
```
Now the application should be running at `http://localhost`.

### 📦 Install a new Python package

1. Install the package using pip:
```bash
pip install <package-name>
```

2. Freeze the current dependencies to `requirements.txt`:
```bash
pip freeze > requirements.txt
```

3. Rebuild the Docker image to include the new package:
```bash
docker-compose build django
```

4. Restart the django Docker container:
```bash
docker-compose up -d
```

### 🛑 Stop the application
To stop the application and remove the containers, run:
```bash
docker-compose down
```

### 📄 Licensing

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

### 🆘 Contact & Support

For any questions or support, please open an issue on GitHub