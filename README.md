# Credit Approval System

This project is a Django-based Credit Approval System that evaluates customer eligibility for loans using historical data. It provides a set of RESTful APIs to register customers, check their loan eligibility, process new loans, and fetch loan-related details.

## 🔧 Features

- Register new customers to the database  
- Evaluate loan eligibility using credit scores  
- Process and store new loan information  
- Retrieve loan and customer details by loan ID  
- View all loans linked to a customer ID  

## 🛠️ Tech Stack

- Django (Backend Framework)  
- PostgreSQL (Database)  
- Docker & Docker Compose (Containerization)  

## 📌 API Overview

All API endpoints are served under api/v1/:

- POST /register/ – Register a new customer  
- POST /check-eligibility/ – Check if a customer is eligible for a loan  
- POST /create-loan/ – Create a loan if the customer is eligible  
- GET /view-loan/<loan_id>/ – Fetch loan and customer details  
- GET /view-loans/<customer_id>/ – View all loans of a particular customer  

**Note:** Always include a trailing slash (`/`) at the end of the URL when making requests.

## 📦 Prerequisites

- Python (for Django development)  
- Docker & Docker Compose  
- Docker Desktop (if you're on Windows/Mac)  

## 🚀 Running the Application

Clone the repository:

```bash
git clone https://github.com/anandkumar16/credit-approval-system.git
cd credit_approval_system

```

Ensure Docker is running, then start the application:
```
docker-compose up --build
```

The APIs will be available at:
```
http://localhost:8000/api/v1/
```
## Testing the APIs
Use this Postman collection with existing APIs to test the project 
🔗 [Collection](https://.postman.co/workspace/My-Workspace~db1fdf29-298d-4d2b-80fb-6819924b1f7f/collection/32656735-08b49174-a1a8-4f57-8ce3-b0981f7f93a2?action=share&creator=32656735)

If using Postman Web, remember to switch to the desktop agent for local requests (bottom right corner in Postman).

Sample data is preloaded from:

- data/customer_data.csv
- data/loan_data.csv

Setting Up a Secret Key
For production environments, create a .env file in the root directory and add a secure Django secret key:

```
from django.core.management.utils import get_random_secret_key
get_random_secret_key()
```
Then, add it to .env:
```
SECRET_KEY=your_generated_key_here
```

