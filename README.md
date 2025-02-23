Backend Developer Assignment – User Data Management & Twitter OAuth API

Table of Contents
	Introduction
	Technology Stack
	Project Setup
	API Documentation
		User Data Management API
		Twitter OAuth Integration
	Postman Collection
	Database Migrations
	Video Demonstration
	Submission Guidelines

Introduction
	This project is a Symfony-based REST API that provides user data management and integrates Twitter OAuth authentication. It includes:
	✅ Uploading CSV files and storing user data in MySQL
	✅ Sending asynchronous email notifications upon successful data storage
	✅ Database backup and restore functionality
	✅ Twitter OAuth login for authentication


Technology Stack
	Language: PHP
	Framework: Symfony 6
	Database: MySQL
	Email Service: Symfony Mailer
	OAuth Library: league/oauth1-client
	Testing Tool: Postman

Project Setup
	1. Clone the Repository
			git clone https://github.com/your-github-username/backend-assignment.git
			cd backend-assignment
	
 	2. Install Dependencies
			composer install

3. Configure Environment Variables

			DATABASE_URL="mysql://root:password@127.0.0.1:3306/backend_db"
			MAILER_DSN=smtp://your-smtp-server
			TWITTER_API_KEY="your_api_key"
			TWITTER_API_SECRET="your_api_secret"

4. Set Up Database
			php bin/console doctrine:database:create
			php bin/console make:migration
			php bin/console doctrine:migrations:migrate

5. Run the Symfony Server
			symfony server:start

API Documentation
		User Data Management API
		1. Upload and Store Data (CSV Upload)
		Endpoint: POST /api/upload
		Request: Upload CSV file (data.csv)
		Response:
		
			{
				  "message": "Users uploaded successfully"
			}

2. View Stored User Data
	Endpoint: GET /api/users
	Response:
	
		[
			{
				"id": 1,
				"name": "John Doe",
				"email": "john@example.com",
				"username": "johndoe",
				"address": "123 Main St",
				"role": "USER"
			}
		]

4. Backup Database
	Endpoint: GET /api/backup
	Response:
	
		{
		  "message": "Database backup created successfully"
		}

5. Restore Database
	Endpoint: POST /api/restore
	Response:
	
		{
		  "message": "Database restored successfully"
		}

Twitter OAuth Integration
	1. Initiate Twitter Authentication
	Endpoint: GET /auth/twitter
	Redirects user to Twitter login page

	2. Handle Twitter Callback
	Endpoint: GET /auth/twitter/callback
	Response:
	
		{
		  "message": "Twitter authentication successful"
		}

Postman Collection
The Postman collection for testing the API is included in the repository under postman_collection.json.

	Open Postman
	Click Import
	Select postman_collection.json
	Run the API requests
	
Database Migrations
	php bin/console doctrine:migrations:migrate

