# 25MCI10090
Name: Yash Karde

--------------------------------------------------

CREATE TABLE Employees (
    emp_id INT,
    emp_name VARCHAR(50),
    manager_id INT,
    department VARCHAR(50),
    salary INT
);

INSERT INTO Employees VALUES
(1, 'Amit', NULL, 'Management', 120000),
(2, 'Ravi', 1, 'Engineering', 80000),
(3, 'Neha', 1, 'Engineering', 82000),
(4, 'Karan', 2, 'Engineering', 60000),
(5, 'Simran', 2, 'Engineering', 62000),
(6, 'Pooja', 3, 'Engineering', 61000),
(7, 'Rahul', 3, 'Engineering', 64000),
(8, 'Arjun', 1, 'HR', 70000);

--------------------------------------------------

SELECT * FROM Employees;

--------------------------------------------------

## Query 1: Employees Working Under Same Manager

SELECT 
    e1.manager_id,
    e1.emp_name AS employee_1,
    e2.emp_name AS employee_2
FROM Employees e1
JOIN Employees e2 
ON e1.manager_id = e2.manager_id
AND e1.emp_id < e2.emp_id
WHERE e1.manager_id IS NOT NULL;

Output:

<img width="609" height="308" alt="image" src="https://github.com/user-attachments/assets/86e868bd-7993-4966-953e-2bccfff4838a" />

--------------------------------------------------

## Query 2: Second Highest Salary

SELECT emp_id, emp_name, salary
FROM Employees
WHERE salary < (SELECT MAX(salary) FROM Employees)
ORDER BY salary DESC
LIMIT 1;

Output:

<img width="443" height="177" alt="image" src="https://github.com/user-attachments/assets/77a9b8f5-8602-45ff-8787-b989e59fab4a" />

--------------------------------------------------
