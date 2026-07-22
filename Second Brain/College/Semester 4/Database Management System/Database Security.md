# Database Security

## Definition

**Database Security** refers to the policies, technologies, and practices used to protect a database from unauthorized access, misuse, modification, disclosure, or destruction. It ensures that data remains **confidential**, **accurate**, **available**, and protected from internal and external threats.

Database security is an essential part of a [[Database Management System (DBMS)]] because databases often store sensitive information such as personal records, financial data, medical records, and business information.

---

## Objectives of Database Security

- Protect confidential data.
- Prevent unauthorized access.
- Maintain data integrity.
- Ensure data availability.
- Prevent data loss.
- Detect malicious activities.
- Comply with legal and organizational requirements.

---

## Importance of Database Security

Database security helps to:

- Protect sensitive information.
- Prevent cyberattacks.
- Maintain customer trust.
- Reduce financial losses.
- Ensure business continuity.
- Meet regulatory compliance requirements.

---

# CIA Triad

The foundation of database security is the **CIA Triad**.

---

## 1. [[Confidentiality]]

Ensures that only authorized users can access data.

Methods:

- Authentication
- Authorization
- Encryption
- Access control

Example:

Only HR staff can view employee salary information.

---

## 2. [[Integrity]]

Ensures that data remains accurate, complete, and unaltered except by authorized users.

Methods:

- Constraints
- Validation
- Checksums
- Transactions
- [[ACID Properties]]

Example:

A student's marks cannot be changed by unauthorized users.

---

## 3. [[Availability]]

Ensures that authorized users can access the database whenever needed.

Methods:

- Backups
- Redundant servers
- Disaster recovery
- Fault tolerance

Example:

Online banking services remain available even during hardware failures.

---

# Threats to Database Security

## Unauthorized Access

Attackers gain access without permission.

---

## SQL Injection

A malicious attack where harmful SQL statements are inserted into application inputs.

Example:

```sql
SELECT * FROM Users
WHERE Username='admin'
AND Password='123';
```

Poor input validation may allow attackers to manipulate the query.

---

## Malware

Malicious software such as:

- Viruses
- Worms
- Ransomware
- Spyware

---

## Insider Threats

Employees or authorized users intentionally or accidentally misuse database access.

---

## Data Theft

Stealing confidential information such as:

- Credit card numbers
- Personal information
- Business records

---

## Data Corruption

Unauthorized modification of stored data.

---

## Denial-of-Service (DoS)

An attack that overwhelms the database, preventing legitimate users from accessing it.

---

## Hardware Failure

Loss of data due to disk crashes or server failures.

---

# Authentication

Authentication verifies the identity of users before granting access.

Common methods:

- Username and password
- Multi-Factor Authentication (MFA)
- Biometrics
- Smart cards
- Digital certificates

---

# Authorization

Authorization determines what authenticated users are allowed to do.

Examples:

- Read data
- Insert records
- Update records
- Delete records
- Create tables

Authorization is commonly managed using SQL commands such as:

```sql
GRANT
REVOKE
```

---

# Access Control

Access control limits database access based on user roles and permissions.

Types include:

### [[Role-Based Access Control (RBAC)]]

Permissions are assigned to roles rather than individual users.

Example:

```
Administrator
Manager
Employee
Student
```

---

### [[Discretionary Access Control (DAC)]]

The owner of an object decides who can access it.

---

### [[Mandatory Access Control (MAC)]]

Access is determined by system-defined security policies and classifications.

---

# Encryption

Encryption converts readable data into an unreadable format.

Only authorized users with the correct key can decrypt the data.

Types:

### Data at Rest

Protects stored database files.

---

### Data in Transit

Protects data transferred over a network.

Protocols:

- SSL
- TLS

---

# Backup and Recovery

Regular backups help restore data after failures.

Types of backups:

- Full Backup
- Incremental Backup
- Differential Backup

Recovery methods include:

- Restore from backup
- Log-based recovery
- Checkpoints

---

# Auditing

Database auditing records user activities for monitoring and investigation.

Audit logs may include:

- Login attempts
- Data modifications
- Failed access attempts
- Permission changes

Benefits:

- Detect suspicious behavior.
- Meet compliance requirements.
- Assist forensic investigations.

---

# Security Best Practices

- Use strong passwords.
- Enable Multi-Factor Authentication.
- Encrypt sensitive data.
- Regularly back up databases.
- Apply software updates and security patches.
- Grant only the minimum required privileges (Principle of Least Privilege).
- Monitor database activity.
- Remove inactive user accounts.
- Validate user inputs to prevent SQL injection.

---

# SQL Security Commands

### [[GRANT]]

Provides privileges to users.

Example:

```sql
GRANT SELECT, INSERT
ON Student
TO Alice;
```

---

### [[REVOKE]]

Removes privileges from users.

Example:

```sql
REVOKE INSERT
ON Student
FROM Alice;
```

---

# Database Security vs Network Security

| Database Security | Network Security |
|-------------------|------------------|
| Protects stored data | Protects network communication |
| Focuses on databases | Focuses on network infrastructure |
| Uses authentication and authorization | Uses firewalls and intrusion detection systems |
| Prevents unauthorized database access | Prevents unauthorized network access |

---

# Advantages

- Protects sensitive information.
- Prevents unauthorized access.
- Maintains data integrity.
- Supports legal compliance.
- Improves customer trust.
- Reduces the risk of cyberattacks.
- Ensures business continuity.

---

# Limitations

- Implementation can be expensive.
- Security measures may reduce performance.
- Requires continuous monitoring.
- Human errors can still compromise security.
- New threats require regular updates.

---

# Applications

- Banking systems
- Hospital management systems
- Government databases
- Educational institutions
- E-commerce platforms
- Cloud databases
- Enterprise information systems
- Financial organizations

---

# Common Database Security Tools

- Authentication systems
- Encryption software
- Firewalls
- Intrusion Detection Systems (IDS)
- Intrusion Prevention Systems (IPS)
- Antivirus software
- Backup and recovery tools
- Database auditing tools

---

# Real-World Examples

### Banking

Protect customer account information using encryption and role-based access control.

---

### Hospital

Allow doctors to access patient records while preventing unauthorized access.

---

### University

Students can view only their own grades, while faculty members can update grades for their courses.

---

## Related Notes

- [[Database Management System (DBMS)]]
- [[Database]]
- [[Database Security]]
- [[Authentication]]
- [[Authorization]]
- [[Access Control]]
- [[Role-Based Access Control (RBAC)]]
- [[Discretionary Access Control (DAC)]]
- [[Mandatory Access Control (MAC)]]
- [[Confidentiality]]
- [[Integrity]]
- [[Availability]]
- [[CIA Triad]]
- [[Encryption]]
- [[SQL Injection]]
- [[GRANT]]
- [[REVOKE]]
- [[Backup]]
- [[Recovery]]
- [[Auditing]]
- [[ACID Properties]]
- [[Transaction Processing]]
- [[Firewall]]
- [[Intrusion Detection System (IDS)]]
- [[Intrusion Prevention System (IPS)]]