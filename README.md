# SQL Injection Prevention Project

## Overview

This project demonstrates a defense mechanism against SQL injection attacks in a banking web application. The application previously allowed unauthorized access to user data through SQL injection vulnerabilities. By implementing safeguards, the SQL queries are now protected from common SQL injection patterns.

## Project Structure

- **SQLInjection.cpp**: Contains the main logic for the project, including query execution and SQL injection prevention mechanisms.
- **sqlite3.c & sqlite3.h**: These files provide an in-memory SQLite database for testing the SQL queries.
- **README.md**: This documentation.

## Objective

The primary objective of this project is to detect, prevent, and mitigate SQL injection attacks. This is achieved by scanning for common SQL injection patterns such as `OR 1=1`, `OR 'hi'='hi'`, and others that always evaluate to true. When such patterns are detected, the application blocks the query from executing and notifies the user about the attempted SQL injection.

## Key Features

1. **SQL Injection Detection**: 
    - The `run_query()` function checks for SQL injection patterns in the input query.
    - The input query is converted to lowercase to ensure case-insensitive matching for potential SQL injection patterns.
    - If an injection is detected, the query is blocked, and a message is displayed in the console notifying the user of the SQL injection.

2. **Prevention**: 
    - By stopping the execution of suspicious queries, the project prevents malicious users from accessing or manipulating sensitive data.

3. **SQLite Database**: 
    - An in-memory SQLite database is used for testing. It contains a `USERS` table with predefined data to simulate the web application's environment.
    
4. **Testing**: 
    - Randomly generated SQL injection attacks are executed, and the output is displayed in the console. Legitimate queries return the expected result, while injection attempts are blocked.

## Usage

1. **Compiling and Running the Project**:
    - Compile the project using your preferred C++ development environment (e.g., Visual Studio, GCC).
    - The project is set up with a main function that initializes the in-memory SQLite database, inserts test data, and runs several SQL queries (some with injections).
    - To run the project, use the following steps in Visual Studio:
      - `Ctrl + F5` to compile and run the program.
      - If any issues occur, check the `Output` or `Error List` in Visual Studio for troubleshooting.

2. **Expected Output**:
    - The project outputs either successful query results or displays messages stating "SQL Injection detected! Query has been blocked" if any injection attempts are found.

## Example Output

