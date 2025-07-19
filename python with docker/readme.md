# 🚀 Demo Python Flask App with Docker

This project demonstrates how to containerize and run a simple Python Flask application using Docker.

---

## 📂 Project Structure

```
.
├── index.py
├── requirements.txt
├── Dockerfile
└── README.md
```

---

## 🐳 Docker Commands

### 🔧 1. Build the Docker Image

```bash
docker build -t debojyoti12022005/demo-python-flask:0.0.1.RELEASE .
```

This command builds the Docker image from the Dockerfile and tags it.

---

### ▶️ 2. Run the Docker Container

```bash
docker container run -d -p 3000:3000 debojyoti12022005/demo-python-flask:0.0.1.RELEASE
```

- `-d`: Run container in detached mode (background)
- `-p 3000:3000`: Map host port `3000` to container port `3000`

---

### ⛔ 3. Stop the Docker Container

```bash
docker container stop <container_id>
```

Replace `<container_id>` with the actual container ID or name. Example:

```bash
docker container stop 4b9cd
```

---

### ☁️ 4. Push the Docker Image to Docker Hub

```bash
docker push debojyoti12022005/demo-python-flask:0.0.1.RELEASE
```

Make sure you're logged in to Docker Hub first:

```bash
docker login
```

---

## 🌐 Access the Flask App

Once the container is running, open your browser and go to:

```
http://localhost:3000
```

---

## 📋 Sample `Dockerfile`

```dockerfile
FROM python:3-alpine3.20

WORKDIR /app
COPY . /app

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 3000

CMD ["python", "./index.py"]
```

---

## 📋 Sample `requirements.txt`

```text
flask
```

---

## 🧪 Sample `index.py`

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello from Flask Docker container!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=3000)
```

---

## 🧰 Prerequisites

- [Docker](https://www.docker.com/products/docker-desktop) installed
- Docker Hub account (if you plan to push the image)

---

## 📄 License

This project is licensed under the MIT License.

---

## 🙌 Author

**Debojyoti Saha**

Feel free to fork and modify this project!
