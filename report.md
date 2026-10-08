# PL/SQL GOTO Statements and Functions: Report

Name:UMWALI Deborah
Student ID: 20252SEN361
Course:Database Development with PL/SQL
Environment: Oracle XE version, SQL Developer

## 1. Purpose
This project practices PL/SQL `GOTO` statements, stored functions, exception handling and calling functions inside SQL queries. It also practices organizing and documenting work on GitHub.

## 2. How to Run
1. Run `00_setup/create_tables.sql`
2. Run all files in `02_functions/`
3. Run all files in `01_goto/`
4. Run all files in `03_tests/`
5. Compare the results with the screenshots in this report.

Run `SET SERVEROUTPUT ON;` first so the output messages are displayed.

## 3. My Test Data
Departments:Finance (10), Sales (20)
Employees:5 employees, salaries from X to Y; one with salary 0 and one without a department to test validation

## 4. Part A: GOTO

### A1: Number Classifier
Task: Classify a number as positive, negative or zero using `GOTO` and labels.
Values tested: 15,-7 and 0
Result:15 a positive number
<img width="244" height="83" alt="go to and tests" src="https://github.com/user-attachments/assets/f1d7fc13-07bd-4875-9ce1-5e638b4bc415" />


### A2: Salary Review
Task: Loop through employees and use `GOTO` to label each salary as low, standard or high.
Thresholds: low below 2 , high above 4 employees
Result: 2 employees low, 1 standard, 2 high

### A3: Illegal GOTO and Fix
Task: Write a `GOTO` that jumps into an `IF` block, show the error, then fix it.
Error shown:
Fix: I moved the label to the same level as the `GOTO`, outside the `IF` block.

Before (error):<img width="317" height="202" alt="Error before corrected" src="https://github.com/user-attachments/assets/36864477-e6ab-49bd-9364-09fa4827abbb" />

After (fixed):

<img width="272" height="101" alt="CORRECTION OF ERROR" src="https://github.com/user-attachments/assets/a8064e6b-9567-4a7e-be59-9fcbe42217f0" />


### A4: Rewrite Without GOTO
Task: Rewrite A1 using `IF / ELSIF / ELSE`.
Result: Same output as A1, with shorter and easier-to-read code.




## 5. Part B: Functions

| Function | Purpose | Error handling |
|---|---|---|
| `fn_annual_salary` | Monthly salary × 12 | Returns NULL if employee not found |
| `fn_years_of_service` | Completed years since hire date | Returns NULL if employee not found |
| `fn_calculate_tax` | Tax using my brackets: [FILL IN] | Raises an error for invalid income |
| `fn_dept_name` | Department name from ID | Returns "Unknown Department" |

### B5: Functions Used in SQL
Task: Call all four functions in one `SELECT`, with a `WHERE` filter on years of service and an `ORDER BY`.

<img width="212" height="142" alt="Functions " src="https://github.com/user-attachments/assets/fb2ff497-3fb6-4f71-9a9d-20845e030ee7" />


## 6. Part C: Combined Task

### C1: Payroll Validator
Task: `fn_validate_payroll` combines the earlier functions and returns `VALID` or an `INVALID` reason.
Rules:  salary above 0, department exists, tax not above income]
Tests: valid employee, salary 0, missing department, non-existent ID (999)


## 7. Challenges and Fixes
ORA-12505 at connection: switched from SID to Service name XEPDB1
Another issue: fix

## 8. What I Learned
- `GOTO` can jump within a block or out of one, but never into an `IF` or `LOOP`.
- Structured code (`IF`, `CASE`, `CONTINUE`) is clearer than `GOTO`.
- Stored functions make logic reusable and can be called inside SQL.
- Exception handling lets functions respond to bad input instead of crashing.

## 9. Conclusion
This assignment taught me to use `GOTO` statements and stored functions in Oracle PL/SQL, to test them with my own data, and to document the work on GitHub.
