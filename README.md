# 5-Tier Voting Application Deployment Using Docker

## Overview
This project demonstrates the deployment of a 5-tier architecture application using Docker. The architecture consists of the following interconnected components:
- **Python (Flask) Frontend**: The voting interface.
- **Redis**: An in-memory data stricture used to queue new votes.
- **.NET Worker**: A background service that consumes votes from Redis and stores them in the backend database.
- **PostgreSQL**: The relational database utilized for persistent storage of voting data.
- **Node.js Frontend**: The results dashboard to display voting tallies in real-time.

## Architecture
This application utilizes a robust 5-tier microservices architecture. Each service operates in an isolated Docker container and interacts through dedicated Docker networks. The process flows seamlessly: a user submits a vote via the Flask frontend, which then queues the data in Redis. The .NET worker continually processes this queue, extracting votes and permanently storing them in the PostgreSQL database. Concurrently, the Node.js application retrieves the updated vote counts from PostgreSQL, rendering them on a live dashboard.

## Steps to Run the Project
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd <repository-name>
   ```
3. Run the complete application stack using Docker Compose:
   ```bash
   docker-compose up -d
   ```
4. Access the web interfaces:
   - **Voting App**: `http://localhost:8080`
   - **Results App**: `http://localhost:8081`

## Ports Used
- **8080**: Voting Application (Flask)
- **8081**: Results Dashboard (Node.js)

## Author
**Yash Patil**
