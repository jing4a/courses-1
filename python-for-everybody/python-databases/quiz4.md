# Quiz 4: Many-to-Many Relationships and Python
9 questions


1. How do we model a many-to-many relationship between two database tables?

- **We add a table with two foreign keys**
- We use the ARRAY column type in both of the tables
- We use a BLOB column in both tables
- We add 10 foreign keys to each table with names like artict_id_1, artist_id2, etc.

2. In Python, what is a database "cursor" most like?

- **A file handle**
- A method within a class
- A function
- A Python dictionary

3. What method do you call in an SQLIte cursor object in Python to run an SQL command?

- socket()
- **execute()**
- send()
- run()

4. In the following SQL,
  cur.execute('SELECT count FROM Counts WHERE org = ? ', (org, ))

what is the purpose of the "?"?

- **It is a placeholder for the contents of the "org" variable**
- It allows more than one boolean operation in the WHERE clause
- It is a syntax error
- It is a search wildcard

5. In the following Python code sequence (assuming cur is a SQLite cursor object),

cur.execute('SELECT count FROM Counts WHERE org = ? ', (org, ))
row = cur.fetchone()

what is the value in row if no rows match the WHERE clause?

- **None**
- -1
- An empty dictionary
- An empty list

6. What does the LIMIT clause in the following SQL accomplish?

SELECT org, count FROM Counts 
   ORDER BY count DESC LIMIT 10

- **It only retrieves the first 10 rows from the table**
- It only sorts on the first 10 characters of the column
- It reverses the sort order if there are more than 10 rows
- It avoids reading data from any table other than Counts

7. What does the executescript() method in the Python SQLite cursor object do that the normal execute() method does not do?

- It allows embeded Python to be executed
- **It allows multiple SQL statements separated by semicolons**
- It allows embedded JavaScript to be executed
- It allows database tables to be created

8. What is the purpose of "OR IGNORE" in the following SQL:

INSERT OR IGNORE INTO Course (title) VALUES ( ? )

- **It makes sure that if a particular title is already in the table, there are no duplicate rows inserted**
- It ignores errors in the SQL syntax for the statement
- It updates the created_at value if the title already exists in the table
- It ignores any foreign key constraint errors

9. For the following Python code to work, what must be added to the title column in the CREATE TABLE statement for the Course table:

cur.execute('''INSERT OR IGNORE INTO Course (title)
    VALUES ( ? )''', ( title, ) )
cur.execute('SELECT id FROM Course WHERE title = ? ', 
    (title, ))
course_id = cur.fetchone()[0]

- A UNIQUE constraint
- A PRIMARY KEY indication
- A NOT NULL constraint - not this one :P
- An AUTOINCREMENT indication

