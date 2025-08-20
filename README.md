Database Setup and Schema Design It demonstrates a simple relational database schema for a Library Management System, including student records, book inventory,

## ⚒️ Table in Task:-

Students : Stores info about students (name, email).
Books : Stores info about books (title, author, available copies).
Issued_Book : Tracks which student has issued which book and when.
Table Relationships

A student can issue many books
A book can be issued by many students
Used FOREIGN KEY to connect tables properly
Tools Used 1.SQL (PostgreSQL) 2.GitHub
## 🗃️ Tables Created

### 1. `Students`
Stores student information.

| Column       | Type          | Constraint           |
|--------------|---------------|----------------------|
| student_id   | INT           | PRIMARY KEY          |
| student_name | VARCHAR(100)  | NOT NULL             |
| email        | VARCHAR(100)  | UNIQUE               |



### 2. `Books`
Stores book information.

| Column          | Type          | Constraint                     |
|-----------------|---------------|--------------------------------|
| book_id         | INT           | PRIMARY KEY                    |
| title           | VARCHAR(255)  | NOT NULL                       |
| author          | VARCHAR(100)  | NOT NULL                       |
| available_books | INT           | CHECK (available_books >= 0)   |



### 3. `issued_book`
Tracks books issued to students.

| Column      | Type   | Constraint                                   |
|-------------|--------|----------------------------------------------|
| issue_id    | SERIAL | PRIMARY KEY                                  |
| student_id  | INT    | FOREIGN KEY → Students(student_id)           |
| book_id     | INT    | FOREIGN KEY → Books(book_id)                 |
| issue_date  | DATE   | NOT NULL                                     |




