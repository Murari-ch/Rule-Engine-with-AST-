# Rule-Engine-with-AST-
Rule Engine with Abstract Syntax Tree (AST)
A Flask-based rule engine designed to evaluate user eligibility based on a set of predefined rules. The engine parses rules through an Abstract Syntax Tree (AST), enabling customizable rule creation, evaluation, and storage.


![Screenshot 2024-10-26 094817](https://github.com/user-attachments/assets/8a72dd3f-9969-45cd-9a14-9cc9ead2dfae)


# Features
Rule Creation: Users can define rules using logical operators and comparisons.
Rule Combination: Combine multiple rules with logical AND or OR operations.
Rule Evaluation: Evaluate a rule against input data to determine if it satisfies the defined conditions.
Data Storage: Uses SQLite to store rules, making it easy to manage and retrieve rules.
Web Interface: Basic UI for interacting with the rule engine.
JSON API: Expose endpoints for creating, viewing, combining, and evaluating rules.

# Technologies
Backend: Python, Flask
Database: SQLite
Frontend: HTML, CSS, JavaScript
Logic: Abstract Syntax Trees (AST) for rule parsing and evaluation
Installation
Prerequisites
Python 3.8+: Ensure you have Python installed. You can check the version with:


# python --version
SQLite: SQLite is generally pre-installed with Python, but you can confirm this by running:


# sqlite3 --version
Setup

# Clone the Repository

git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# Create a Virtual Environment (Optional)

python -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate     # On Windows

# Install Dependencies

pip install -r requirements.txt

# Initialize the Database

python -c "from api import init_db; init_db()"
Configuration
Modify any necessary configurations (e.g., port, debug mode) in api.py.

# Usage
Run the Application

# Start the Flask server with:

python api.py
This should start the server, and you’ll see a message like:

Running on http://127.0.0.1:5000/
Web Interface
Visit http://127.0.0.1:5000/ in your browser to access the web interface.

# API Endpoints
1. Create a Rule
Endpoint: POST /api/create_rule
Request:
json

{
  "name": "Example Rule",
  "rule": "age > 18 AND income >= 50000"
}
Response:
json

{
  "rule_id": 1,
  "name": "Example Rule",
  "ast": { "type": "operator", "value": "and", ... }
}
2. View All Rules
Endpoint: GET /api/view_rules
Response:
json

[
  { "id": 1, "name": "Example Rule", "rule": "age > 18 AND income >= 50000", "ast": "{...}" }
]
3. Combine Rules
Endpoint: POST /api/combine_rules
Request:
json

{
  "rule_ids": [1, 2],
  "names": "Combined Rule"
}
Response:
json

{
  "combined_rule_id": 3,
  "names": "Combined Rule",
  "combined_ast": { "type": "operator", "value": "and", ... }
}
4. Evaluate a Rule
Endpoint: POST /api/evaluate_rule
Request:
json

{
  "rule_id": 1,
  "data": { "age": 25, "income": 60000 }
}
Response:
json

{ "result": true }

# Project Structure

.
├── api.py                  # Main application file
├── logic.py                # Rule parsing and evaluation logic
├── requirements.txt        # Project dependencies
├── templates/
│   └── index.html          # Frontend HTML file
├── static/
│   └── style.css           # CSS for frontend styling
└── rules.db                # SQLite database file

# Troubleshooting
Server Doesn’t Start:

Ensure you’re in the correct directory: cd path/to/project
Confirm Flask is installed in your environment: pip show flask
Database Not Initialized:

Run python -c "from api import init_db; init_db()"

# Contributing
I would love some contributions!
