<h1>
  <span class="headline">Building a CICD Pipeline with Jenkins in Docker</span>
  <span class="subhead">Setup</span>
</h1>

## Setup

This lesson requires two separate repositories of starter code. One provides the environment to run Jenkins inside Docker, and the other contains a Node.js and React application that you’ll use to build and test with Jenkins. By preparing both repositories, you’ll have a complete setup for practicing CI/CD concepts.

## Jenkins + Docker Environment

**Repository:** [building-a-cicd-pipline-with-jenkins-in-docker-starter-code](https://git.generalassemb.ly/modular-curriculum-all-courses/building-a-cicd-pipline-with-jenkins-in-docker-starter-code)

**What This Repo Is For:**  
This repository sets up a fully functional Jenkins instance inside Docker containers. It includes Docker Compose files that let you choose between pre-built images for a quick start or build-your-own images for more customization. Once running, this environment makes it easy to experiment with CI/CD workflows—creating pipelines, running jobs, and exploring Jenkins features.

### 1. Fork and clone:

- **Sign In:** Make sure you’re logged into your GA enterprise GitHub account.
- **Fork:** Navigate to the repo link above and fork it into your own GA enterprise GitHub account.
- **Clone:** Copy the SSH or HTTPS URL from your newly forked repository and run:
  ```bash
  git clone <your-forked-jenkins-docker-repo-url>
  ```
  Navigate into the cloned directory:
  ```bash
  cd <your-forked-jenkins-docker-repo-folder>
  ```

### 2. Run Jenkins in Docker:

- Start Jenkins by running:

  ```bash
  docker-compose up -d node
  ```

  This command spins up the Jenkins environment in Docker containers, running in the background (detached mode).

- After running the `docker-compose` command, verify that your Jenkins container is running:

  ```bash
  docker ps
  ```

### 3. Verify Jenkins:

- Once the containers are up, open your browser and go to:
  ```
  http://localhost:8080
  ```
- Log into Jenkins using:
  - **Username:** admin
  - **Password:** admin

You now have a Jenkins environment ready for configuring CI/CD tasks.

---

## Node.js + React Application

**Repository:** [simple-node-js-react-npm-app](https://git.generalassemb.ly/modular-curriculum-all-courses/simple-node-js-react-npm-app)

**What This Repo Is For:**  
This repository provides a simple Node.js and React application as your “application under test.” You will integrate this app into your Jenkins pipeline—running builds, tests, and eventually delivering the application. It’s a basic “Welcome to React” style app, ideal for practicing pipeline stages without complex application logic.

### 1. Fork and clone:

- **Sign In:** Ensure you’re logged into your GA enterprise GitHub account.
- **Fork:** Go to the repo link above and fork it into your GA enterprise GitHub account.
- **Clone:** From your forked repository, copy the SSH or HTTPS URL and run:
  ```bash
  git clone <your-forked-node-react-repo-url>
  ```
  Navigate into the cloned directory:
  ```bash
  cd <your-forked-node-react-repo-folder>
  ```

### 2. Prepare for pipeline integration:

- After cloning, you have a local copy of the application. You’ll use this code with Jenkins to configure and run a CI/CD pipeline—installing dependencies, running tests, and even deploying the app.
