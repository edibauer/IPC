## init
### Table to flat file (Complete)
```sql
-- First create a departments table if it doesn't exist
CREATE TABLE departments (
    dept_id     NUMBER PRIMARY KEY,
    dept_name   VARCHAR2(50) NOT NULL
);

-- Create the table
CREATE TABLE staff (
    emp_id      NUMBER PRIMARY KEY,
    first_name  VARCHAR2(50) NOT NULL,
    last_name   VARCHAR2(50) NOT NULL,
    email       VARCHAR2(100) UNIQUE,
    hire_date   DATE DEFAULT SYSDATE,
    salary      NUMBER(10,2),
    dept_id     NUMBER,
    job_title   VARCHAR2(100),
    manager_id  NUMBER,
    CONSTRAINT fk_dept FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
);

-- Insert sample departments
INSERT INTO departments VALUES (10, 'Administration');
INSERT INTO departments VALUES (20, 'Marketing');
INSERT INTO departments VALUES (30, 'IT');
INSERT INTO departments VALUES (40, 'Finance');
INSERT INTO departments VALUES (50, 'Operations');

-- Insert 15 employee records
INSERT INTO employees VALUES (101, 'John', 'Smith', 'john.smith@company.com', TO_DATE('15-JUN-2018', 'DD-MON-YYYY'), 85000, 30, 'Software Engineer', NULL);
INSERT INTO employees VALUES (102, 'Sarah', 'Johnson', 'sarah.j@company.com', TO_DATE('22-MAR-2019', 'DD-MON-YYYY'), 92000, 20, 'Marketing Manager', NULL);
INSERT INTO employees VALUES (103, 'Michael', 'Williams', 'michael.w@company.com', TO_DATE('05-JAN-2020', 'DD-MON-YYYY'), 78000, 30, 'Database Admin', 101);
INSERT INTO employees VALUES (104, 'Emily', 'Brown', 'emily.b@company.com', TO_DATE('12-SEP-2017', 'DD-MON-YYYY'), 110000, 40, 'Finance Director', NULL);
INSERT INTO employees VALUES (105, 'David', 'Jones', 'david.j@company.com', TO_DATE('30-APR-2021', 'DD-MON-YYYY'), 65000, 50, 'Operations Analyst', NULL);
INSERT INTO employees VALUES (106, 'Jessica', 'Garcia', 'jessica.g@company.com', TO_DATE('18-JUL-2019', 'DD-MON-YYYY'), 72000, 20, 'Marketing Specialist', 102);
INSERT INTO employees VALUES (107, 'Daniel', 'Miller', 'daniel.m@company.com', TO_DATE('03-NOV-2020', 'DD-MON-YYYY'), 95000, 30, 'Senior Developer', 101);
INSERT INTO employees VALUES (108, 'Olivia', 'Davis', 'olivia.d@company.com', TO_DATE('25-FEB-2018', 'DD-MON-YYYY'), 82000, 10, 'HR Manager', NULL);
INSERT INTO employees VALUES (109, 'James', 'Rodriguez', 'james.r@company.com', TO_DATE('14-AUG-2021', 'DD-MON-YYYY'), 68000, 50, 'Logistics Coordinator', 105);
INSERT INTO employees VALUES (110, 'Sophia', 'Martinez', 'sophia.m@company.com', TO_DATE('09-MAY-2019', 'DD-MON-YYYY'), 75000, 30, 'Systems Analyst', 101);
INSERT INTO employees VALUES (111, 'Alexander', 'Hernandez', 'alex.h@company.com', TO_DATE('27-DEC-2017', 'DD-MON-YYYY'), 105000, 40, 'Financial Analyst', 104);
INSERT INTO employees VALUES (112, 'Emma', 'Lopez', 'emma.l@company.com', TO_DATE('06-OCT-2020', 'DD-MON-YYYY'), 88000, 20, 'Content Strategist', 102);
INSERT INTO employees VALUES (113, 'William', 'Wilson', 'william.w@company.com', TO_DATE('22-JAN-2021', 'DD-MON-YYYY'), 70000, 30, 'Junior Developer', 101);
INSERT INTO employees VALUES (114, 'Ava', 'Anderson', 'ava.a@company.com', TO_DATE('17-MAR-2018', 'DD-MON-YYYY'), 79000, 10, 'Executive Assistant', 108);
INSERT INTO employees VALUES (115, 'Ethan', 'Thomas', 'ethan.t@company.com', TO_DATE('08-JUL-2019', 'DD-MON-YYYY'), 87000, 50, 'Operations Manager', NULL);

COMMIT;

```
