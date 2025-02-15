# 🚀 FastAPI Beyond CRUD

FastAPI Beyond CRUD is a scalable and production-ready FastAPI-based application, designed to go beyond basic CRUD operations. It includes authentication, database integration, Redis caching, and email notifications.

## 📦 Prerequisites 
✅ **Docker**
---

## 📌 Getting Started

**1. Clone the Repository**
```sh
git clone https://github.com/ztao-8/fastapi-beyond-CRUD.git
cd fastapi-beyond-CRUD
```

**2. Set Up a Virtual Environment**
```sh
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
```

**3. Install Dependencies**
```sh
pip install -r requirements.txt
```

**4. Set Up Environment Variables**  
Create a `.env` file in the root directory:
```ini
# Database configuration
DATABASE_URL=postgresql+asyncpg://postgres:testpass@db:5432/bookly

# JWT authentication settings
JWT_SECRET=your_jwt_secret_key
JWT_ALGORITHM=HS256

# Redis settings
REDIS_HOST=redis
REDIS_PORT=6379
REDIS_URL=redis://redis:6379

# Email configuration (for notifications)
MAIL_USERNAME=your_email@example.com
MAIL_PASSWORD=your_email_password
MAIL_SERVER=smtp.sendgrid.net
MAIL_PORT=587
MAIL_FROM=your_email@example.com
MAIL_FROM_NAME=FastAPI App

# App domain
DOMAIN=http://localhost:8000
```

**5. Start the Application**
```sh
uvicorn src.main:app --reload
```
✅ The API will be available at: **`http://localhost:8000`**

---

## 🚀 Run with Docker

**1. Build & Run the Containers**
```sh
docker-compose up --build
```

**2. Access the API**
- **API Docs:** `http://localhost:8000/docs`
- **Redoc:** `http://localhost:8000/redoc`

---

## 📜 API Documentation

Once the server is running, visit:  
🔹 **Swagger UI:** [`http://localhost:8000/docs`](http://localhost:8000/docs)  
🔹 **ReDoc UI:** [`http://localhost:8000/redoc`](http://localhost:8000/redoc)

---

## 🧪 Running Tests

**1. Run Tests Locally**
```sh
pytest
```

**2. Run Tests Inside Docker**
```sh
docker-compose run web pytest
```

---

## ⚡ GitHub Actions & CI/CD

This project uses **GitHub Actions** for continuous integration and deployment.

**🔹 Features:**
- **Nightly Build:** Scheduled CI/CD every 5 minutes (`cron: "*/5 * * * *"`)
- **Run Tests on PRs**
- **Automatic Docker Image Build & Push to GitHub Container Registry (GHCR)**

**🔹 Manually Trigger CI/CD**  
If you want to manually trigger the workflow:
1. Go to **GitHub Actions**
2. Select **Nightly Build**
3. Click **"Run workflow"**

---

## 🐳 Pushing Docker Image to GitHub Container Registry (GHCR)

This project pushes Docker images to **GitHub Container Registry (GHCR)**.

**1. Log in to GHCR**
```sh
echo "${GHCR_PAT}" | docker login ghcr.io -u "ztao-8" --password-stdin
```

**2. Build & Push Image**
```sh
docker build -t ghcr.io/ztao-8/fastapi-beyond-crud:latest .
docker push ghcr.io/ztao-8/fastapi-beyond-crud:latest
```

**3. Check Image in GitHub Packages**
- **GitHub Repo Packages:** [`https://github.com/ztao-8/fastapi-beyond-CRUD/packages`](https://github.com/ztao-8/fastapi-beyond-CRUD/packages)
- **List All Packages:**
  ```sh
  gh api -H "Accept: application/vnd.github.v3+json" /users/ztao-8/packages/container
  ```

---

## 🛠 Contributing

Want to contribute? Follow these steps:

1. **Fork the repository**
2. **Clone your fork**
   ```sh
   git clone https://github.com/your-username/fastapi-beyond-CRUD.git
   ```
3. **Create a feature branch**
   ```sh
   git checkout -b feature-name
   ```
4. **Make changes and commit**
   ```sh
   git add .
   git commit -m "feat: Added new feature"
   ```
5. **Push to GitHub**
   ```sh
   git push origin feature-name
   ```
6. **Open a Pull Request!**

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 🎯 Author

👤 **Zoe Tao**  
🔗 **GitHub:** [ztao-8](https://github.com/ztao-8)  
📧 **Email:** `ztao8@dons.usfca.edu`
