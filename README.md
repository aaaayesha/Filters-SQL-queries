# Applying Filters to SQL queries

# Project description
My organization is working to make their system more secure. It is my job as a Cybersecurity analyst to ensure the system is safe, to  investigate all potential security issues and to update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.


# Retrieve after hours failed login attempts

We recently discovered a potential security incident that occurred after business hours. To investigate this, we need to query the log_in_attempts table and review after hours login activity. 
We used filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. 
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.


<img width="915" height="802" alt="Screenshot 2025-09-28 212720" src="https://github.com/user-attachments/assets/5c064fff-cc4e-489a-9772-8fb47a77c710" />

The success column in the log_in_attempts table contains values of TRUE or FALSE to indicate whether the login was successful. MySQL stores Boolean values as 1 for TRUE, and 0 for FALSE. This means that TRUE is represented as 1, and FALSE represented as 0 in the success column.
