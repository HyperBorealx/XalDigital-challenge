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
     
 **1.1 Identify Entities:**
        Person:
        Attributes: first_name, last_name
     
        Company:
        Attributes: company_name
        Address:
        Attributes: address, city, state, zip
     
        Contact:    
        Attributes: phone1, phone2, email
     
        Department:
        Attributes: department
     
  **1.2 Identify Relationships:**
        Person-Contact Relationship:
        A person can have multiple contact details.
        Relationship Attributes: None
        
        Person-Address Relationship:
        A person can have one or more addresses.
        Relationship Attributes: None
        
        Company-Address Relationship:
        A company can have one or more addresses.
        Relationship Attributes: None
        
        Company-Contact Relationship:
        A company can have multiple contact details.
        Relationship Attributes: None
        Person-Department Relationship:
        
        A person belongs to a specific department.
        Relationship Attributes: None

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

