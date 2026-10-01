# Node.js CI/CD with GitHub Actions & Docker

A simple Node.js application demonstrating a basic **CI/CD pipeline using GitHub Actions, Docker, and Docker Hub**.

## 🚀 Pipeline

```text
Git Push
   ↓
GitHub Actions
   ↓
Install Dependencies
   ↓
Run Jest Tests
   ↓
Build Docker Image
   ↓
Push Image to Docker Hub
```

## 🛠️ Technologies

* Node.js
* Express.js
* Jest
* Docker
* Docker Hub
* GitHub Actions
* Git & GitHub

## 📁 Project Structure

```text
nodejs-demo-app/
├── .github/
│   └── workflows/
│       └── main.yml
├── Dockerfile
├── package.json
├── package-lock.json
├── server.js
└── server.test.js
```

## 🧪 Testing

Run tests locally:

```bash
npm test
```

The project includes a Jest test for the `/health` endpoint.

## 🐳 Docker

Build the image:

```bash
docker build -t nodejs-demo-app:1.0 .
```

Run the container:

```bash
docker run -d --name nodejs-demo-app -p 3000:3000 nodejs-demo-app:1.0
```

Test:

```text
http://localhost:3000/health
```

## 🔄 GitHub Actions

The workflow automatically:

1. Checks out the code
2. Sets up Node.js 20
3. Installs dependencies using `npm ci`
4. Runs Jest tests
5. Logs into Docker Hub
6. Builds the Docker image
7. Pushes the image to Docker Hub

Docker Hub credentials are stored securely using GitHub Actions Secrets:

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

## 🚀 Deployment

The Docker image was successfully pulled from Docker Hub and deployed locally using Docker.

### AWS EC2 Deployment

The automated EC2 deployment step was **not implemented because an AWS account/EC2 environment was unavailable during development**.

The planned flow is:

```text
GitHub Actions
      ↓
Docker Hub
      ↓
AWS EC2
      ↓
Docker Pull
      ↓
Docker Run
      ↓
Application
```

## ✅ Completed

* GitHub repository
* Jest testing
* GitHub Actions CI pipeline
* Docker image build
* Docker Hub push
* Local Docker deployment

**Future:** Add automated AWS EC2 deployment when an EC2 environment is available.
