# pd4768-DATAB-1 Damian Szkudlarek
**Schema (MySQL v5.7)**

    CREATE TABLE patients (
        id INT PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        date_of_birth DATE NOT NULL,
        email VARCHAR(255) UNIQUE,
        phone_number VARCHAR(20),
        weight DECIMAL(5,2),
        height INT
    );
    INSERT INTO patients (id, name, date_of_birth, email, phone_number, weight, height)
    VALUES 
        (1, 'John Doe', '1985-06-15', 'john.doe@gmail.com', '1234567890', 72.50, 180),
        (2, 'Jane Smith', '1990-09-22', 'jane.smith@gmail.com', '0987654321', 60.00, 170),
        (3, 'James Brown', '1978-12-05', 'james.brown@gmail.com', '1122334455', 80.00, 175),
        (4, 'Emily Davis', '2000-04-10', 'emily.davis@gmail.com', '2233445566', 55.00, 165);
    

---

**Query #1**

    SELECT * FROM patients;

| id  | name        | date_of_birth | email                 | phone_number | weight | height |
| --- | ----------- | ------------- | --------------------- | ------------ | ------ | ------ |
| 1   | John Doe    | 1985-06-15    | john.doe@gmail.com    | 1234567890   | 72.50  | 180    |
| 2   | Jane Smith  | 1990-09-22    | jane.smith@gmail.com  | 0987654321   | 60.00  | 170    |
| 3   | James Brown | 1978-12-05    | james.brown@gmail.com | 1122334455   | 80.00  | 175    |
| 4   | Emily Davis | 2000-04-10    | emily.davis@gmail.com | 2233445566   | 55.00  | 165    |

---
**Query #2**

    
    
    SELECT * FROM patients WHERE weight > 65;

| id  | name        | date_of_birth | email                 | phone_number | weight | height |
| --- | ----------- | ------------- | --------------------- | ------------ | ------ | ------ |
| 1   | John Doe    | 1985-06-15    | john.doe@gmail.com    | 1234567890   | 72.50  | 180    |
| 3   | James Brown | 1978-12-05    | james.brown@gmail.com | 1122334455   | 80.00  | 175    |

---
**Query #3**

    
    
    SELECT * FROM patients ORDER BY height DESC;

| id  | name        | date_of_birth | email                 | phone_number | weight | height |
| --- | ----------- | ------------- | --------------------- | ------------ | ------ | ------ |
| 1   | John Doe    | 1985-06-15    | john.doe@gmail.com    | 1234567890   | 72.50  | 180    |
| 3   | James Brown | 1978-12-05    | james.brown@gmail.com | 1122334455   | 80.00  | 175    |
| 2   | Jane Smith  | 1990-09-22    | jane.smith@gmail.com  | 0987654321   | 60.00  | 170    |
| 4   | Emily Davis | 2000-04-10    | emily.davis@gmail.com | 2233445566   | 55.00  | 165    |

**Schema (MySQL v5.7)**

    CREATE TABLE patients (
        id INT PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        date_of_birth DATE NOT NULL,
        email VARCHAR(255) UNIQUE,
        phone_number VARCHAR(20),
        weight DECIMAL(5,2),
        height INT
    );
    INSERT INTO patients (id, name, date_of_birth, email, phone_number, weight, height)
    VALUES 
        (1, 'John Doe', '1985-06-15', 'john.doe@gmail.com', '1234567890', 72.50, 180),
        (2, 'Jane Smith', '1990-09-22', 'jane.smith@gmail.com', '0987654321', 60.00, 170),
        (3, 'James Brown', '1978-12-05', 'james.brown@gmail.com', '1122334455', 80.00, 175),
        (4, 'Emily Davis', '2000-04-10', 'emily.davis@gmail.com', '2233445566', 55.00, 165);
    

---

**Query #1**

    UPDATE patients
    SET email = 'john.updated@gmail.com'
    WHERE name = 'John Doe';

There are no results to be displayed.

---
**Query #2**

    
    
    DELETE FROM patients WHERE id = 3;

There are no results to be displayed.

---
**Query #3**

    
    
    ALTER TABLE patients ADD blood_type CHAR(3);

There are no results to be displayed.

---
**Query #4**

    
    
    UPDATE patients SET blood_type = '0+' WHERE name = 'John Doe';

There are no results to be displayed.

---
**Query #5**

    
    UPDATE patients SET blood_type = 'AB+' WHERE name = 'Jane Smith';

There are no results to be displayed.

---
**Query #6**

    
    UPDATE patients SET blood_type = 'A-' WHERE name = 'James Brown';

There are no results to be displayed.

---
**Query #7**

    
    UPDATE patients SET blood_type = 'B+' WHERE name = 'Emily Davis';

There are no results to be displayed.

---
**Query #8**

    
    
    SELECT * FROM patients;

| id  | name        | date_of_birth | email                  | phone_number | weight | height | blood_type |
| --- | ----------- | ------------- | ---------------------- | ------------ | ------ | ------ | ---------- |
| 1   | John Doe    | 1985-06-15    | john.updated@gmail.com | 1234567890   | 72.50  | 180    | 0+         |
| 2   | Jane Smith  | 1990-09-22    | jane.smith@gmail.com   | 0987654321   | 60.00  | 170    | AB+        |
| 4   | Emily Davis | 2000-04-10    | emily.davis@gmail.com  | 2233445566   | 55.00  | 165    | B+         |

---
**Query #9**

    
    
    SELECT * FROM patients ORDER BY id DESC LIMIT 2 OFFSET 0;

| id  | name        | date_of_birth | email                 | phone_number | weight | height | blood_type |
| --- | ----------- | ------------- | --------------------- | ------------ | ------ | ------ | ---------- |
| 4   | Emily Davis | 2000-04-10    | emily.davis@gmail.com | 2233445566   | 55.00  | 165    | B+         |
| 2   | Jane Smith  | 1990-09-22    | jane.smith@gmail.com  | 0987654321   | 60.00  | 170    | AB+        |

---

[View on DB Fiddle](https://www.db-fiddle.com/)
