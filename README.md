# Applying Filters to SQL queries

# Project description
My organization is working to make their system more secure. It is my job as a Cybersecurity analyst to ensure the system is safe, to  investigate all potential security issues and to update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.


# Retrieve after hours failed login attempts

We recently discovered a potential security incident that occurred after business hours. To investigate this, we need to query the log_in_attempts table and review after hours login activity. 
We used filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. 
The success column in the log_in_attempts table contains values of TRUE or FALSE to indicate whether the login was successful. 
MySQL stores Boolean values as 1 for TRUE, and 0 for FALSE. This means that TRUE is represented as 1, and FALSE represented as 0 in the success column.
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.


<img width="915" height="802" alt="Screenshot 2025-09-28 212720" src="https://github.com/user-attachments/assets/5c064fff-cc4e-489a-9772-8fb47a77c710" />


The first part of my screenshot is the query i used, and the second part is a portion of the output. 
This query filters for failed login attempts that occurred after 18:00. 
First, I started by selecting all data from the log_in_attempts table. 
Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. 
The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. 
The second condition is success = 0 or FALSE, which filters for the failed login attempts. 

# Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. To investigate this event, we review all login attempts which occurred on this day and the day before. I used filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08. (The date of the login attempt is found in the login_date column.)

<img width="921" height="373" alt="Screenshot 2" src="https://github.com/user-attachments/assets/ebf689ac-fc3b-491b-ab72-a8c2b51188c4" />

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.


# Retrieve login attempts outside of Mexico

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.
The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.

<img width="917" height="318" alt="Screenshot 3" src="https://github.com/user-attachments/assets/1d0327fd-9bd5-4db2-bfb4-e03f44e56b41" />

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE. 

# Retrieve employees in Marketing

My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

<img width="941" height="215" alt="image" src="https://github.com/user-attachments/assets/57705c6b-6e14-4051-aee2-62fdbee09047" />

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

# Retrieve employees in Finance or Sales

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

<img width="936" height="236" alt="image" src="https://github.com/user-attachments/assets/9f0399cd-ccc1-4e4c-ad88-277e8b468c99" />

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

# Retrieve all employees not in IT

My team needs to make one more security update on employees who are not in the Information Technology department. 
To make the update, I first have to get information on these employees.
The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department.

<img width="938" height="268" alt="image" src="https://github.com/user-attachments/assets/a1c33d9b-7b5e-4ae3-9d45-72f5915eb022" />

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

Summary

I applied filters to SQL queries to get specific information on login attempts and employee machines. 
I used two different tables, log_in_attempts and employees. 
I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.

