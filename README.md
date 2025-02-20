


## Introduction
Welcome to the Chat Assistant! This is a simple Chat Assistant built using Flask and SQLite. It allows users to interact with an employee database using natural language queries. The assistant understands and responds to common queries related to employees, departments, managers, and salaries.

## Installation and Setup

1. Install dependencies:
   ```sh
   pip install flask
   ```
2. Create an SQLite database named `chat_assistant.db` and set up the required tables:
   ```sql
   CREATE TABLE Employees (
       ID INTEGER PRIMARY KEY AUTOINCREMENT,
       Name TEXT,
       Department TEXT,
       Hire_Date TEXT,
       Salary INTEGER
   );
   
   CREATE TABLE Departments (
       ID INTEGER PRIMARY KEY AUTOINCREMENT,
       Name TEXT,
       Manager TEXT
   );
   ```
3. Run the Flask application:
   ```sh
   python app.py
   ```


## API Usage 🔧
The `/query` endpoint accepts a JSON payload with a query string. Example request:
```json
{
    "query": "which employee is from Engineering department"
}
```
Example response:
```json
{
    "employees": ["Alice", "Bob"]
}
```


## Contributing 🤝
Feel free to contribute by raising issues or submitting pull requests! 🙌

## License 📜
This project is open-source and available under the MIT License. 🎉
