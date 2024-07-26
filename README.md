# Quiz Application

This is a simple quiz application built with FastAPI, SQLAlchemy, and PostgreSQL. The application allows users to create questions with multiple choices.

## Requirements

- Python 3.10 or later
- PostgreSQL
- pip (Python package installer)

## Installation

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd fastapi-postgres

2.**Create a virtual environment:**
  
    bash
    python -m venv .env

3.**Activate the virtual environment:**

Windows:

    bash
    env\Scripts\activate

Linux/MacOS:

    bash
    source .env/bin/activate

4.**Install the dependencies:**

    bash
    pip install -r requirements.txt

5.**Set up the PostgreSQL database:**

  Make sure PostgreSQL is installed and running.
  Create a new database:

    sql
    CREATE DATABASE quizapplication;

6.**Update the database URL in database.py:**

    python
    URL_DATABASE  = 'postgresql://postgres:<your-password>@localhost:5432/quizapplication'

7.**Running the Application**

  7.1**Start the FastAPI application using Uvicorn:**

    bash
    uvicorn main:app --reload

  7.2**Open your browser and navigate to the following URLs:**
        Swagger UI: http://127.0.0.1:8000/docs
        ReDoc: http://127.0.0.1:8000/redoc
        Root URL: http://127.0.0.1:8000

API Endpoints
Create a Question

  URL: /questions
  Method: POST
  
  Request Body:

    json
    {
      "question_text": "What is the capital of France?",
      "choices": [
        {"choice_text": "Paris", "is_correct": true},
        {"choice_text": "London", "is_correct": false},
        {"choice_text": "Berlin", "is_correct": false}
      ]
    }

Response:

    json

    {
      "message": "Question created successfully"
    }

Project Structure


    fastapi-postgres
    ├── main.py
    ├── models.py
    ├── database.py
    ├── requirements.txt
    └── README.md

  main.py: The main FastAPI application file.
  models.py: Contains SQLAlchemy models for the application.
  database.py: Database connection and session management.
  requirements.txt: List of dependencies.
  README.md: Project documentation.

Troubleshooting

  "Not Found" Error on Root URL:
      This is expected if no route is defined for the root URL. Ensure you have the route defined in main.py.

  Validation Errors:
      Ensure your request body matches the expected schema defined in Pydantic models (QuestionBase and ChoiceBase).

License

This project is licensed under the MIT License.

    Feel free to modify this `README.md` file according to your specific requirements and preferences.

