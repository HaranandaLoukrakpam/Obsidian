# Database System Architecture

## Definition

**Database System Architecture** refers to the structure and organization of the components of a [[Database Management System (DBMS)]]. It describes how users, applications, the [[DBMS]], and the database interact to store, retrieve, and manage data efficiently.

A well-designed database architecture ensures **data independence**, **security**, **consistency**, **scalability**, and **efficient data access**.

---

## Objectives of Database System Architecture

- Organize data efficiently.
- Provide secure data access.
- Support multiple users simultaneously.
- Ensure data consistency and integrity.
- Minimize data redundancy.
- Achieve data independence.
- Improve system performance.

---

## Components of a Database System

A database system consists of the following components:

### [[Database]]

A structured collection of related data.

Examples:

- Student records
- Employee information
- Banking transactions

---

### [[Database Management System (DBMS)]]

Software that allows users to create, store, retrieve, update, and manage databases.

Examples:

- [[MySQL]]
- [[PostgreSQL]]
- [[Oracle Database]]
- [[Microsoft SQL Server]]
- [[SQLite]]

---

### [[Database Users]]

People or applications that interact with the database.

Types:

- Database Administrator (DBA)
- Application programmers
- End users
- System analysts

---

### [[Application Programs]]

Software that communicates with the DBMS.

Examples:

- Banking systems
- Hospital management systems
- E-commerce websites

---

### [[Hardware]]

Physical devices used to run the database system.

Examples:

- Servers
- Storage devices
- Network equipment

---

## Three-Schema Architecture

The ANSI/SPARC model divides a database into **three levels** to achieve **data independence**.

```
Users
   │
External Level
   │
Conceptual Level
   │
Internal Level
   │
Physical Storage
```

---

## 1. External Level (View Level)

The **External Level** is the highest level of abstraction.

It defines how individual users view the database.

### Characteristics

- Multiple user views.
- Hides unnecessary information.
- Provides security.
- Different users may have different views.

Example:

A student can view only their own marks, while a teacher can view marks of all students.

---

## 2. Conceptual Level (Logical Level)

The **Conceptual Level** describes the complete logical structure of the database.

It includes:

- Tables
- Relationships
- Constraints
- Data types

It does **not** describe how data is physically stored.

### Characteristics

- Single logical view of the entire database.
- Defines entities and relationships.
- Independent of physical storage.

---

## 3. Internal Level (Physical Level)

The **Internal Level** describes how data is physically stored on storage devices.

It includes:

- File organization
- Indexing
- Storage blocks
- Access methods
- Record placement

### Characteristics

- Lowest level of abstraction.
- Focuses on storage efficiency.
- Invisible to end users.

---

## Data Independence

One of the primary goals of the three-schema architecture is **data independence**.

### [[Physical Data Independence]]

The ability to change the internal storage structure without affecting the conceptual schema.

Examples:

- Changing indexing methods.
- Reorganizing files.
- Upgrading storage hardware.

---

### [[Logical Data Independence]]

The ability to modify the conceptual schema without affecting user views or application programs.

Examples:

- Adding a new column.
- Creating new tables.
- Modifying relationships.

---

## DBMS Architecture Types

### One-Tier Architecture

The user directly accesses the database.

```
User
   │
Database
```

Characteristics:

- Simple architecture.
- Mainly used for local applications.
- No network communication.

Examples:

- SQLite applications.

---

### Two-Tier Architecture

The client communicates directly with the database server.

```
Client
   │
Database Server
```

Characteristics:

- Better performance than one-tier.
- Used in desktop database applications.
- Client sends SQL queries directly.

Examples:

- Desktop applications using MySQL.

---

### Three-Tier Architecture

The client communicates with an application server, which then communicates with the database.

```
Client
      │
Application Server
      │
Database Server
```

Characteristics:

- Most common architecture.
- Improved security.
- Better scalability.
- Easier maintenance.
- Supports large web applications.

Examples:

- Banking systems
- E-commerce websites
- Social media platforms

---

## DBMS Functional Components

### [[Query Processor]]

Processes SQL queries submitted by users.

Functions:

- Query parsing
- Query optimization
- Query execution

---

### [[Storage Manager]]

Manages the physical storage of data.

Functions:

- File management
- Buffer management
- Index management
- Disk space allocation

---

### [[Transaction Manager]]

Ensures that database transactions follow the [[ACID Properties]].

Responsibilities:

- Concurrency control
- Recovery
- Consistency

---

### [[Authorization Manager]]

Controls user authentication and permissions.

Responsibilities:

- Access control
- User authentication
- Privilege management

---

### [[Data Dictionary]]

A repository that stores metadata about the database.

Contains:

- Table definitions
- Constraints
- Relationships
- User permissions

---

## Advantages of Three-Schema Architecture

- Data independence.
- Better security.
- Easier maintenance.
- Multiple user views.
- Improved scalability.
- Reduced application dependency.

---

## Limitations

- More complex implementation.
- Slight processing overhead.
- Higher development cost.
- Requires proper schema design.

---

## Applications

- Banking systems
- Hospital management systems
- University databases
- Airline reservation systems
- Inventory management
- E-commerce platforms
- Government information systems

---

## One-Tier vs Two-Tier vs Three-Tier

| Feature | One-Tier | Two-Tier | Three-Tier |
|----------|----------|----------|------------|
| Client directly accesses database | Yes | Yes | No |
| Application server | No | No | Yes |
| Security | Low | Medium | High |
| Scalability | Low | Medium | High |
| Maintenance | Difficult | Moderate | Easy |
| Typical Use | Local applications | Desktop applications | Enterprise and web applications |

---

## Three Levels of Database Architecture

| Level | Description |
|--------|-------------|
| [[External Level]] | User-specific view of the database |
| [[Conceptual Level]] | Logical structure of the entire database |
| [[Internal Level]] | Physical storage of the database |

---

## Real-World Examples

### Banking System

- Customers view only their accounts (External Level).
- The bank defines all account relationships (Conceptual Level).
- Data is stored on disks using indexes and files (Internal Level).

---

### University Database

- Students access grades.
- Teachers manage course information.
- Administrators maintain the complete database structure.

---

## Related Notes

- [[Database Management System (DBMS)]]
- [[Database]]
- [[Database System Architecture]]
- [[Three-Schema Architecture]]
- [[External Level]]
- [[Conceptual Level]]
- [[Internal Level]]
- [[Physical Data Independence]]
- [[Logical Data Independence]]
- [[Query Processor]]
- [[Storage Manager]]
- [[Transaction Manager]]
- [[Authorization Manager]]
- [[Data Dictionary]]
- [[ACID Properties]]
- [[SQL]]
- [[MySQL]]
- [[PostgreSQL]]
- [[Oracle Database]]
- [[Microsoft SQL Server]]
- [[SQLite]]