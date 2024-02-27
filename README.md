# XalDigital-challenge
## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Functionality](#functionality)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Running the Project Locally](#running-the-project-locally)
- [AWS Deployment](#aws-deployment)
- [Contributing](#contributing)
- [License](#license)

## Overview

The project consists of the following components:

- **Database:** PostgreSQL database to store data.
- **Lambda Function:** AWS Lambda function written in Node.js to interact with the database.
- **API Gateway:** AWS API Gateway to expose RESTful endpoints for data retrieval and manipulation.

## Project Structure
data-engineer-challenge/
├── docker-compose.yml # Docker Compose file for local development
├── src/
│ ├── lambda_function.js # AWS Lambda function code
│ └── other_source_files...
├── template.yaml # AWS SAM template for infrastructure as code
├── README.md # Project documentation


## Functionality

1. **Database Setup:**
   - Designed PostgreSQL database schema based on provided data.
   - Created tables for `person`, `company`, `address`, `contact`, and `department`.

2. **Lambda Function:**
   - Implemented AWS Lambda function to interact with the database.
   - Supports CRUD operations (Create, Read, Update, Delete) for the `person` table.
   - Utilizes environment variables for database connection details.

3. **API Gateway:**
   - Configured API Gateway to expose RESTful endpoints.
   - Endpoints:
     - `GET /records`: Retrieve all records.
     - `POST /records`: Create a new record (example data required).

## Getting Started

### Prerequisites

- Docker and Docker Compose for local development.
- AWS CLI and SAM CLI for AWS deployment.

