# Sinbad

A containerized Ruby on Rails web application developed for restaurant operations, featuring delivery platform integration, automated continuous integration, and production deployment workflows.

---

## Tech Stack and Architecture

* **Backend:** Ruby 3.4.8 and Ruby on Rails
* **Containerization:** Docker (`Dockerfile`, `.dockerignore`)
* **Deployment and Infrastructure:** Kamal (configured via `.kamal/` for setup, pre-build execution, deployment, and proxy management)
* **CI/CD:** GitHub Actions (`.github/workflows/ci.yml` and `docker-publish.yml`) for automated testing and container publishing

---

## Core Features

* **Restaurant Operations:** Built on a standard Rails architecture (`app/`) structured for menu management, order processing, and core business logic.
* **Delivery Integration:** Includes configuration and setup documentation for third-party delivery services, specifically Uber Eats (`UBER_EATS_SETUP.md`).
* **Asset Management:** Manages static media and brand assets, including product imagery (`beef-kabab.png`).

---

## Getting Started

### Prerequisites

* Ruby 3.4.8
* Bundler
* Docker and Docker Compose
* Kamal (for production infrastructure management)

### Local Development Setup

1. Clone the repository:
```bash
git clone https://github.com/your-username/shawarma-sinbad.git
cd shawarma-sinbad

```


2. Install dependencies:
```bash
bundle install

```


3. Initialize and migrate the database:
```bash
bin/rails db:create db:migrate

```


4. Start the local server:
```bash
bin/rails server

```



---

## Deployment

Deployment is managed using **Kamal** for containerized delivery to production servers.

* **Configuration:** Server settings and deployment hooks reside in the `.kamal/` directory.
* **Operations:** Kamal handles initialization, pre-build routines, container deployment, and proxy management.

---

## Continuous Integration and Deployment

Automated GitHub Actions workflows maintain code quality and deployment standards:

* **CI (`ci.yml`):** Executes test suites and validation checks on pull requests and pushes.
* **Docker Publish (`docker-publish.yml`):** Builds and pushes production-ready container images to the registry.
