# Project 4: CI/CD Pipeline with GitHub Actions & Docker

## Objective
Set up a CI/CD pipeline that builds a Docker image for a Node.js app, runs tests, and deploys locally.

## Tools
- Node.js
- Docker
- GitHub Actions
- Docker Hub
- Minikube (optional for Kubernetes testing)

## Project Structure
```
app/
├── index.js
test/
├── app.test.js
.github/
└── workflows/
    └── ci.yml
Dockerfile
package.json
```

## Step-by-Step Guide

### Step 1: Clone the Repo
```bash
git clone https://github.com/your-user/node-ci-cd-app.git
cd node-ci-cd-app
```

### Step 2: Initialize Node App
```bash
npm init -y
npm install --save-dev jest
```

### Step 3: Write App Code
A simple HTTP server is in `app/index.js`.

### Step 4: Write Test Case
Basic test in `test/app.test.js`.

### Step 5: Dockerize the App
Use the `Dockerfile` to build the container image.

### Step 6: Set up GitHub Actions
Configure `.github/workflows/ci.yml` for:
- Installing dependencies
- Running tests
- Building and pushing Docker image

### Step 7: Push to GitHub
Make sure Docker credentials are set in GitHub Secrets:
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

### Step 8: Run the Container
```bash
docker run -p 3000:3000 yourdockerhubusername/node-ci-cd-app
```

### Step 9: Access App
Visit `http://localhost:3000` to confirm deployment.
