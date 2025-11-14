# DevOps_TASK1


# Node.js CI/CD Demo with GitHub Actions

A minimal Node.js + Express demo that demonstrates a CI/CD pipeline using **GitHub Actions** and **Docker**.

---

## Features
- Node.js (v18) + Express
- Automated tests with `npm test` (Jest or your test runner)
- Dockerized application
- CI/CD pipeline (runs tests, builds Docker image, pushes to DockerHub)

---

## Requirements
- Node.js 18
- npm
- Docker (for local build/run)
- GitHub repository with the following secrets configured:
  - `DOCKER_USERNAME` — your DockerHub username
  - `DOCKER_PASSWORD` — your DockerHub password or access token

---

## Install & Run Locally
```bash
# install dependencies
npm install

# run the app
npm start
Open http://localhost:3000 (or the port your app uses).

Run with Docker (locally)
bash
Copy code
# build image
docker build -t nodejs-ci-cd-demo .

# run container
docker run -p 3000:3000 nodejs-ci-cd-demo
CI/CD (GitHub Actions)
The repository includes a workflow that triggers on push and pull_request to the main branch. The workflow:

Checks out the code

Sets up Node.js 18

Installs dependencies (npm install)

Runs tests (npm test)

Builds Docker image: ${{ secrets.DOCKER_USERNAME }}/nodejs-ci-cd-demo:latest

Logs into DockerHub using DOCKER_USERNAME and DOCKER_PASSWORD

Pushes the image to DockerHub

Make sure the main branch exists and the secrets are added in Repository → Settings → Secrets.

Project Structure (example)
bash
Copy code
.
├── src/
│   ├── app.js
│   └── ...
├── tests/
│   └── app.test.js
├── Dockerfile
├── package.json
└── .github/workflows/ci-cd.yml


