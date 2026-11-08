CodeCraftHub Learning Management System
A simple personalized learning platform for developers to track courses they want to learn. This project was built using Python and Flask, focusing on REST API basics without the need for complex databases.

Features
Add new courses with target completion dates

View all your tracked courses

Update course information and progress status

Delete courses you no longer need

JSON file-based storage (no database setup required)

RESTful API design with proper error handling

Installation
Create a new directory and navigate into it:

Bash
mkdir codecrafthub
cd codecrafthub
Create and activate a virtual environment:

Windows: python -m venv venv then venv\Scripts\activate

Mac/Linux: python -m venv venv then source venv/bin/activate

Install Python dependencies:

Bash
pip install -r requirements.txt
Running the Application
Start the Flask server by running:

Bash
python app.py
The API will be available at http://localhost:5000. The courses.json file will be created automatically upon the first request.

API Endpoints
1. Add a Course
Method: POST

Endpoint: /api/courses

JSON Payload Example:

JSON
{
  "name": "Python Basics",
  "description": "Learn Python fundamentals",
  "target_date": "2026-12-31",
  "status": "Not Started"
}
2. Get All Courses
Method: GET

Endpoint: /api/courses

3. Get Specific Course
Method: GET

Endpoint: /api/courses/<id>

4. Update Course
Method: PUT

Endpoint: /api/courses/<id>

JSON Payload Example (all fields optional):

JSON
{
  "status": "In Progress"
}
5. Delete Course
Method: DELETE

Endpoint: /api/courses/<id>

Testing
You can use curl commands in your terminal or tools like Postman to interact with the API.(Note for Windows CMD users: Use double quotes for the JSON payload and escape inner quotes like this: \")

Troubleshooting
Problem: ModuleNotFoundError: No module named 'flask'

Solution: Ensure your virtual environment is activated and run pip install -r requirements.txt.

Problem: Address already in use or Port 5000 is busy

Solution: Stop other running applications that might be using port 5000, or change the port directly at the bottom of app.py.

Project Structure
Plaintext
codecrafthub/
├── app.py              # Main Flask application logic and routing
├── courses.json        # JSON database (auto-generated)
├── requirements.txt    # Python package dependencies
└── README.md           # Project documentation