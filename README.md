# Rule-Engine-with-AST-
Rule Engine with Abstract Syntax Tree (AST)
A Flask-based rule engine designed to evaluate user eligibility based on a set of predefined rules. The engine parses rules through an Abstract Syntax Tree (AST), enabling customizable rule creation, evaluation, and storage.
![Screenshot 2024-10-26 094817](https://github.com/user-attachments/assets/8a72dd3f-9969-45cd-9a14-9cc9ead2dfae)




# Key Components
Flask Application (api.py): Serves as the main application interface, handling API requests and serving the UI.
Logic (logic.py): Contains the logic for processing and evaluating rules, leveraging AST to parse and assess rule syntax.
Database (rules.db): Stores rule definitions and user attributes to allow easy querying and rule management.
Templates and Static Files: Provides a simple UI for users to interact with the rule engine.
Getting Started
Prerequisites
Ensure you have Python installed on your machine. Install project dependencies by running:

# pip install -r requirements.txt
Running the Application
To start the Flask application, navigate to the project directory and execute:

# python AST/api.py
Accessing the Application
After running, the application will be accessible at http://localhost:5000.

# Usage
Define Rules: Rules are stored in rules.db, where each rule specifies user eligibility criteria based on attributes (e.g., age, department, income).
Rule Evaluation: logic.py leverages AST to parse and evaluate the defined rules.
User Interface: The UI (index.html and styles.css) enables users to input criteria and view eligibility outcomes.
Contributing
Contributions are welcome! Feel free to submit a pull request or open an issue.

