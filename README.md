# Chat-Assistant-for-for-SQLite-Database
To evaluate your ability to design, implement, and deploy a chat assistant that interacts with an SQLite database to answer user queries.

# Connect to the SQLite database (or create it if it doesn't exist)
conn = sqlite3.connect('company.db')
cursor = conn.cursor()

# Create the Employees table
cursor.execute('''
CREATE TABLE IF NOT EXISTS Employees (
    ID INTEGER PRIMARY KEY,
    Name TEXT,
    Department TEXT,
    Salary INTEGER,
    Hire_Date TEXT
)
''')

# Create the Departments table
cursor.execute('''
CREATE TABLE IF NOT EXISTS Departments (
    ID INTEGER PRIMARY KEY,
    Name TEXT,
    Manager TEXT
)
''')

# Insert sample data into the Employees table
cursor.executemany('''
INSERT INTO Employees (ID, Name, Department, Salary, Hire_Date)
VALUES (?, ?, ?, ?, ?)
''', [
    (1, 'Alice', 'Sales', 50000, '2021-01-15'),
    (2, 'Bob', 'Engineering', 70000, '2020-06-10'),
    (3, 'Charlie', 'Marketing', 60000, '2022-03-20')
])

# Insert sample data into the Departments table
cursor.executemany('''
INSERT INTO Departments (ID, Name, Manager)
VALUES (?, ?, ?)
''', [
    (1, 'Sales', 'Alice'),
    (2, 'Engineering', 'Bob'),
    (3, 'Marketing', 'Charlie')
])

# Commit the changes and close the connection
conn.commit()
conn.close()
