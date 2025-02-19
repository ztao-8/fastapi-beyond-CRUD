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

**2. Update Environment Variables**  
Update a`.env.example` file in the root directory with your own information:
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

**3. Set up environment variables by copying the example configuration**
```bash
    cp .env.example .env
```
---

## 🚀 Run with Docker

**1. Build & Run the Containers**
```sh
docker compose up --build
```

**2. Access the API**
- **API Docs:** `http://localhost:8000/docs`


## 🧪 Running Tests

**2. Run Tests Inside Docker**
```sh
docker compose run web pytest
```


---
## ⚡ GitHub Actions & CI/CD

This project uses **GitHub Actions** for continuous integration and deployment.

**🔹 Features:**
- **Conventional Commits: Check commits style once a PR is open**
- **Automatic Close PR: If commits don't satisfy standard style PR will close**
- **Nightly Build:** Scheduled CI/CD every night (`cron: "0 0 * * *"`)
- **Run Tests**
- **Automatic Docker Image Build & Push to GitHub Container Registry (GHCR)**
- **Send Email Notification When test failed or commits are not conventional**

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

## 🛠 Sending Email if test fail/not conventional commits

How to send an email notification? Follow these steps:

1. **SendGrid Account:**
    Sign up for a free SendGrid account at sendgrid.com.
2. **API Key**
Once signed up, generate an API key by going to the Settings > API Keys section of the SendGrid dashboard. Make sure to copy this key and store it securely. You’ll need it later.
3. **Verified Sender Email:**
SendGrid requires a verified sender email. This is typically the email you used to sign up for the SendGrid account, or any email address you’ve verified in the Sender Authentication section of the dashboard.
4. **Update your information**
Go to your git repo, open Settings > Secrets and variables > Actions, update "SENDGRID_API_KEY" with your onw key.
Also, Go to workflow files, update "from email" and "to email" with your emails.
---

## 📄 License

This project is licensed under the **MIT License**.

---

