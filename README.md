
# 🐳 Dockerize Python Flask Application

This project demonstrates how to Dockerize a simple **Python Flask** application, providing an isolated and reproducible environment that runs seamlessly across different systems. Docker helps eliminate dependency conflicts, making deployment and scaling effortless.

---

## 🔍 Overview

With the growing demand for containerized applications, it's crucial for developers and DevOps engineers to learn how to package and deploy apps using Docker. This project showcases how to:

- Build a Docker image for a Flask app
- Run the app inside a Docker container
- Access the app from a browser or command line
- Automate the entire process using a shell script

---

## 🧩 Tech Stack

- Python 3.9
- Flask 3.0.0
- Docker

---

## 🧠 Problem Statement

Deploying a Python Flask app on different machines often leads to:

- Dependency mismatches
- Manual configuration errors
- Inconsistent environments

Using Docker, we create a **containerized environment** that eliminates such issues, allowing the app to run the same way everywhere.

---

## 🎯 Objectives

- 🐳 Dockerize a Python Flask app
- 📦 Package all dependencies into a Docker image
- ▶️ Run the app with a single command
- 🌐 Access via browser or CLI
- 🧪 Automate using a build & run script

---

## 📂 Project Structure

```
Dockerize-python-flask-application-/
├── app.py              # Flask application
├── requirements.txt    # Dependencies
├── Dockerfile          # Image build instructions
└── demo_project.sh     # Script to build & run the app
```

---

## ⚙️ Setup Instructions

### ✅ Prerequisites

- Docker installed on your system  
- Basic knowledge of Docker and Python

---

### 🔧 1. Clone the Repository

```bash
git clone https://github.com/Ratan456-star/Dockerize-python-flask-application-.git
cd Dockerize-python-flask-application-
```

---

### 🏗️ 2. Build the Docker Image

```bash
docker build -t my-flask-app .
```

---

### 🚀 3. Run the Docker Container

```bash
docker run -p 5000:5000 my-flask-app
```

---

### 🔍 4. Verify the Output

#### Option A: Using curl

```bash
curl localhost:5000
```

#### Option B: Open in Browser

```
http://localhost:5000/
```

You should see:

```
Hello from Flask inside Docker!
```

---

### 🧪 Bonus: One-click Script Execution

Use the provided `demo_project.sh` script:

```bash
chmod +x demo_project.sh
./demo_project.sh
```

This will:
- Build the image
- Run the container in detached mode
- Wait 20 seconds
- Auto-verify via `curl`

---

## 📜 File Details

### Dockerfile

```Dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY . /app
RUN pip install --no-cache-dir -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]
```

---

### app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return "Hello from Flask inside Docker!"

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=5000)
```

---

### requirements.txt

```
Flask==3.0.0
```

---

### demo_project.sh

```bash
#!/bin/bash

# Build Docker image
docker build -t my-flask-app .

# Run container
docker run -d -p 5000:5000 my-flask-app

echo "Wait 20s for application up!"
sleep 20

# Verify output
curl localhost:5000
```

---

## 🔗 Resources

- [Flask Documentation](https://pypi.org/project/Flask/)
- [Docker Official Site](https://www.docker.com/)
- [DevOps Basics on Docker](https://github.com/tungbq/devops-basic/blob/main/topics/docker/README.md)

---

## 👨‍💻 Author

[Ratan456-star](https://github.com/Ratan456-star)

---

## ✅ Output

```bash
$ curl localhost:5000
Hello from Flask inside Docker!
```
![Dockerized_flask_application](https://github.com/user-attachments/assets/e88a0141-b627-47de-96e1-9882b53212bd)

---

## 📄 License

MIT License – feel free to use, modify, and share!

