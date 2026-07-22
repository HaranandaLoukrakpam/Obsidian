# Relational Languages and Database Design

## Definition

**Relational Languages** are languages used to create, manipulate, retrieve, and control data stored in a **Relational Database Management System (RDBMS)**. The most widely used relational language is **[[SQL (Structured Query Language)]]**.

**Database Design** is the process of planning and organizing a database to efficiently store data while minimizing redundancy, ensuring data integrity, and improving performance.

---

# Relational Languages

## Definition

Relational languages are used to interact with relational databases. They allow users to:

- Create databases and tables.
- Insert, update, and delete records.
- Retrieve data.
- Control user access.
- Manage database transactions.

The standard relational language is **[[SQL (Structured Query Language)]]**.

---

## Types of SQL Languages

SQL is divided into five major categories:

### [[Data Definition Language (DDL)]]

Used to define and modify the structure of database objects.

Common Commands:

| Command | Purpose |
|----------|---------|
| `CREATE` | Create database objects |
| `ALTER` | Modify existing objects |
| `DROP` | Delete objects |
| `TRUNCATE` | Remove all rows while keeping the table |
| `RENAME` | Rename database objects |

Example:

```sql
CREATE TABLE Student (
    StudentID INT,
    Name VARCHAR(50),
    Age INT
);
```

---

### [[Data Manipulation Language (DML)]]

Used to manipulate data stored in tables.

Commands:

| Command | Purpose |
|----------|---------|
| `INSERT` | Add new records |
| `UPDATE` | Modify records |
| `DELETE` | Remove records |

Example:

```sql
INSERT INTO Student
VALUES (1,'Alice',20);
```

---

### [[Data Query Language (DQL)]]

Used to retrieve data from a database.

Main command:

```sql
SELECT
```

Example:

```sql
SELECT * FROM Student;
```

---

### [[Data Control Language (DCL)]]

Used to control user permissions.

Commands:

| Command | Purpose |
|----------|---------|
| `GRANT` | Give privileges |
| `REVOKE` | Remove privileges |

---

### [[Transaction Control Language (TCL)]]

Used to manage database transactions.

Commands:

| Command | Purpose |
|----------|---------|
| `COMMIT` | Save changes |
| `ROLLBACK` | Undo changes |
| `SAVEPOINT` | Create a rollback point |

---

## SQL Clauses

Common SQL clauses include:

- `WHERE`
- `ORDER BY`
- `GROUP BY`
- `HAVING`
- `DISTINCT`
- `LIMIT`
- `JOIN`

Example:

```sql
SELECT Name
FROM Student
WHERE Age > 18
ORDER BY Name;
```

---

## Relational Algebra

**[[Relational Algebra]]** is a procedural query language that forms the theoretical foundation of SQL.

Basic operations include:

- Selection (σ)
- Projection (π)
- Union (∪)
- Difference (−)
- Cartesian Product (×)
- Join (⨝)
- Rename (ρ)

---

## Relational Calculus

**[[Relational Calculus]]** is a non-procedural query language where users specify **what** data is required rather than **how** to retrieve it.

Types:

- [[Tuple Relational Calculus (TRC)]]
- [[Domain Relational Calculus (DRC)]]

---

# Database Design

## Definition

Database design is the process of creating the logical and physical structure of a database to efficiently organize and manage data.

Good database design reduces redundancy, improves consistency, and enhances performance.

---

## Objectives of Database Design

- Minimize redundancy.
- Maintain data integrity.
- Improve efficiency.
- Ensure consistency.
- Simplify maintenance.
- Support scalability.
- Improve security.

---

## Database Design Process

### 1. Requirement Analysis

Identify:

- Users
- Data requirements
- Business rules
- Functional requirements

---

### 2. Conceptual Design

Create an [[Entity-Relationship (ER) Model]].

Identify:

- Entities
- Attributes
- Relationships

---

### 3. Logical Design

Convert the ER model into relational tables.

Determine:

- Primary keys
- Foreign keys
- Constraints

---

### 4. Normalization

Organize data to reduce redundancy and dependency.

Common normal forms:

- [[First Normal Form (1NF)]]
- [[Second Normal Form (2NF)]]
- [[Third Normal Form (3NF)]]
- [[Boyce-Codd Normal Form (BCNF)]]

---

### 5. Physical Design

Define:

- Indexes
- Storage structures
- File organization
- Performance optimization

---

## Entity-Relationship Model

The [[Entity-Relationship (ER) Model]] is a graphical representation of database structure.

Components:

### [[Entity]]

A real-world object.

Examples:

- Student
- Employee
- Product

---

### [[Attribute]]

Describes an entity.

Examples:

- Name
- Age
- Salary

---

### [[Relationship]]

Represents associations between entities.

Examples:

- Student enrolls in Course.
- Employee works in Department.

---

## Keys

### [[Primary Key]]

Uniquely identifies each record.

Example:

```
StudentID
```

---

### [[Foreign Key]]

References the primary key of another table.

Used to establish relationships.

---

### [[Candidate Key]]

A field that can uniquely identify records.

---

### [[Composite Key]]

A primary key made up of two or more attributes.

---

## Constraints

Constraints enforce data integrity.

Common constraints:

- `NOT NULL`
- `UNIQUE`
- `PRIMARY KEY`
- `FOREIGN KEY`
- `CHECK`
- `DEFAULT`

---

## Normalization

Normalization reduces redundancy and improves consistency.

### [[First Normal Form (1NF)]]

- No repeating groups.
- Atomic values only.

---

### [[Second Normal Form (2NF)]]

- Must satisfy 1NF.
- Remove partial dependencies.

---

### [[Third Normal Form (3NF)]]

- Must satisfy 2NF.
- Remove transitive dependencies.

---

### [[Boyce-Codd Normal Form (BCNF)]]

A stronger version of 3NF where every determinant is a candidate key.

---

## Advantages of Good Database Design

- Reduced redundancy.
- Improved consistency.
- Easier maintenance.
- Better performance.
- Stronger security.
- Easier scalability.
- Simplified querying.

---

## Limitations

- Initial design takes time.
- Complex databases require careful planning.
- Over-normalization may reduce performance.
- Requires domain knowledge.

---

## Applications

- Banking systems
- Hospital management systems
- E-commerce websites
- University databases
- Inventory systems
- Airline reservation systems
- Government databases

---

## SQL Categories Summary

| SQL Category | Purpose |
|--------------|---------|
| [[Data Definition Language (DDL)]] | Define database objects |
| [[Data Manipulation Language (DML)]] | Modify data |
| [[Data Query Language (DQL)]] | Retrieve data |
| [[Data Control Language (DCL)]] | Manage permissions |
| [[Transaction Control Language (TCL)]] | Manage transactions |

---

## Database Design Workflow

```
Requirement Analysis
          ↓
Conceptual Design (ER Model)
          ↓
Logical Design
          ↓
Normalization
          ↓
Physical Design
          ↓
Database Implementation
```

---

## Real-World Examples

- Designing a university database with Students, Courses, and Enrollments.
- Creating an e-commerce database with Customers, Products, and Orders.
- Developing a hospital database for Patients, Doctors, and Appointments.
- Building a banking database for Customers, Accounts, and Transactions.

---

## Related Notes

- [[Database Management System (DBMS)]]
- [[Relational Database]]
- [[SQL (Structured Query Language)]]
- [[Data Definition Language (DDL)]]
- [[Data Manipulation Language (DML)]]
- [[Data Query Language (DQL)]]
- [[Data Control Language (DCL)]]
- [[Transaction Control Language (TCL)]]
- [[Relational Algebra]]
- [[Relational Calculus]]
- [[Tuple Relational Calculus (TRC)]]
- [[Domain Relational Calculus (DRC)]]
- [[Entity-Relationship (ER) Model]]
- [[Entity]]
- [[Attribute]]
- [[Relationship]]
- [[Primary Key]]
- [[Foreign Key]]
- [[Candidate Key]]
- [[Composite Key]]
- [[Normalization]]
- [[First Normal Form (1NF)]]
- [[Second Normal Form (2NF)]]
- [[Third Normal Form (3NF)]]
- [[Boyce-Codd Normal Form (BCNF)]]