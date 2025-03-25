# Weather Analysis

## Problem Statement

We have a table that stores daily weather data for the last six months of 2020. This includes maximum, minimum, and average temperatures.  

Your task is to write a query that retrieves the following details for each month:
- `month` (numerical representation)
- `monthly maximum temperature`
- `monthly minimum temperature`
- `monthly average temperature` (rounded to the nearest integer)

### Expected Output  
The output should contain the following columns:  

| month | max  | min  | avg |
|-------|------|------|-----|
| 7     | 100  | 67   | 79  |

---

## Schema

### **Table: `temperature_records`**

| Column      | Type        | Description                               |
|------------|------------|-------------------------------------------|
| record_date | varchar(10) | Date of the record (YYYY-MM-DD format)  |
| data_type   | varchar(3)  | Type of temperature (`'min'`, `'max'`, or `'avg'`) |
| data_value  | int        | Temperature value                        |

---

## Constraints
- Each day has three temperature records: `max`, `min`, and `avg`.
- The dataset only contains data for the last 6 months of 2020.
- The `avg` value must be **rounded to the nearest integer**.

---

## Sample Input (Table: `temperature_records`)

| record_date  | data_type | data_value |
|-------------|----------|-----------|
| 2020-07-01  | max      | 92        |
| 2020-07-01  | min      | 71        |
| 2020-07-01  | avg      | 74        |
| 2020-07-02  | max      | 90        |
| 2020-07-02  | min      | 67        |
| 2020-07-02  | avg      | 77        |

---

## Expected Output

| month | max  | min  | avg |
|-------|------|------|-----|
| 7     | 100  | 67   | 79  |

---

## Notes
- Extract the `month` from the `record_date`.
- Use SQL aggregate functions (`MAX`, `MIN`, `AVG`).
- The `avg` column must be **rounded**.
