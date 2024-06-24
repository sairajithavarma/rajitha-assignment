# Simple Web Application CI/CD Pipeline

## Overview

This repository contains a simple web application with a frontend (React) and backend (Flask), containerized using Docker. The CI/CD pipeline is implemented using GitHub Actions, and the application is deployed to AWS ECS. Monitoring and logging are set up using Prometheus and Grafana.

## Setup and Deployment

### Prerequisites

- AWS account with ECS service enabled
- Docker and Docker Compose installed
- GitHub account
- Docker Hub account

### Steps

1. **Clone the repository**:
    ```sh
    git clone https://github.com/yourusername/your-repo.git
    cd your-repo
    ```

2. **Build and run Docker containers locally**:
    ```sh
    docker-compose up
    ```

3. **Push code to GitHub**:
    ```sh
    git add .
    git commit -m "Initial commit"
    git push origin master
    ```

4. **Set up GitHub Actions**:
    - Add Docker Hub credentials, AWS credentials, and other required secrets to your GitHub repository settings.

5. **Deploy to AWS ECS**:
    - Create an ECS cluster and services for frontend and backend.
    - Create and register task definitions with the respective Docker images.

6. **Set up Prometheus and Grafana**:
    - Update the Prometheus configuration file with the correct targets.
    - Run the monitoring stack using Docker Compose:
      ```sh
      docker-compose -f monitoring/docker-compose.yml up -d
      ```

## Monitoring and Logging

Prometheus is used for monitoring the application, and Grafana is used for visualizing the metrics. The monitoring setup includes configurations to scrape metrics from the Flask backend and Nginx frontend.

### Accessing Grafana

After starting the monitoring stack, Grafana can be accessed at `http://localhost:3000`.

## Diagram

![CI/CD Pipeline and Deployment Architecture](./docs/architecture-diagram.png)

## Authors

- Your Name

## License

This project is licensed under the MIT License.

