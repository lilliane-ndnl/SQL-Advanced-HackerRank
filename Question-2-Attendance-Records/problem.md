# Weekend Hours Worked

## Problem Statement

The times that employees log in and out are recorded over the course of a month.  
For each employee, determine the number of hours worked during the weekends.  
For simplicity, hours worked in a day are truncated to their integer part.

### Example  
For instance:  
- 10 hours between `'2000-01-01 00:45:00'` and `'2000-01-01 10:45:00'`.  
- 9 hours between `'2000-01-01 00:46:00'` and `'2000-01-01 10:45:00'`.  

### Expected Output
Return a list of employee IDs and their total weekend hours worked, sorted in descending order.

---

## Schema

### **Table: `attendance`**

| Column     | Type         | Description                                  |
|------------|-------------|----------------------------------------------|
| timestamp  | varchar(20) | Date and time when the employee logged in/out |
| emp_id     | int         | Unique ID of the employee                   |

---

## Constraints
- Each employee will have multiple timestamps.
- Employees log in and out at different times.
- Only consider **Saturday (5) and Sunday (6)** as weekends.
- Pair each login timestamp with the next logout timestamp.

---

## Sample Input (Table: `attendance`)

| timestamp           | emp_id |
|---------------------|--------|
| 2021-07-03 08:36:00 | 747    |
| 2021-07-03 17:40:00 | 747    |
| 2021-07-04 08:37:00 | 747    |
| 2021-07-04 17:38:00 | 747    |
| 2021-07-10 08:33:00 | 747    |
| 2021-07-10 17:54:00 | 747    |

---

## Expected Output

| emp_id | work_hours |
|--------|-----------|
| 747    | 75        |
| 904    | 74        |
| 425    | 73        |
| 107    | 72        |
| 878    | 70        |

---

## Notes
- Ensure that timestamps are correctly **paired** (IN and OUT).
- Only consider **weekend timestamps** in calculations.
- Work hours should be truncated to their integer part.
