# XalDigital-challenge
## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Functionality](#functionality)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
- [AWS Deployment](#aws-deployment)

## Overview

The project consists of the following components:

- **Database:** PostgreSQL database to store data.
- **Lambda Function:** AWS Lambda function written in Node.js to interact with the database.
- **API Gateway:** AWS API Gateway to expose RESTful endpoints for data retrieval and manipulation.


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

## AWS Deployment
Package and deploy the Lambda function using SAM:
sam package --s3-bucket <your-s3-bucket> --output-template-file packaged.yaml
sam deploy --template-file packaged.yaml --stack-name data-engineer-stack --region <your-region> --capabilities CAPABILITY_IAM
Update the API Gateway in the AWS Console with the new Lambda function URL.

