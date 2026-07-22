# Transaction Processing

## Definition

**Transaction Processing** is the process of executing one or more database operations as a single logical unit of work. A transaction ensures that the database remains **accurate**, **consistent**, and **reliable**, even in the presence of system failures or concurrent users.

A transaction typically consists of operations such as **INSERT**, **UPDATE**, **DELETE**, and **SELECT** performed together.

---

## What is a Transaction?

A **transaction** is a sequence of one or more database operations that are executed as a single unit.

A transaction must either:

- Complete successfully (**Commit**), or
- Be completely undone (**Rollback**)

This ensures that the database is never left in an inconsistent state.

---

## Example

### Bank Money Transfer

Suppose ₹5,000 is transferred from **Account A** to **Account B**.

Operations:

```text
Account A = Account A - 5000
Account B = Account B + 5000
```

If the system crashes after deducting money from Account A but before adding it to Account B, the transaction must be **rolled back** to prevent data inconsistency.

---

## States of a Transaction

A transaction passes through several states during execution.

### 1. Active State

The transaction is currently executing.

---

### 2. Partially Committed State

The transaction has executed all operations but has not yet been permanently saved.

---

### 3. Committed State

The transaction has completed successfully, and changes are permanently stored in the database.

---

### 4. Failed State

The transaction encounters an error or system failure and cannot continue.

---

### 5. Aborted State

The transaction is rolled back, and the database returns to its previous consistent state.

---

## Transaction State Diagram

```text
          Active
             │
             ▼
   Partially Committed
        │         │
        ▼         ▼
   Committed    Failed
                    │
                    ▼
                Aborted
```

---

# ACID Properties

The correctness of transactions is ensured by the **[[ACID Properties]]**.

---

## 1. [[Atomicity]]

**Atomicity** means **all operations of a transaction must be completed or none at all**.

Example:

Money transfer:

```text
Debit A
Credit B
```

If one operation fails, both are cancelled.

---

## 2. [[Consistency]]

A transaction must take the database from one valid state to another while preserving all rules and constraints.

Example:

Total money before transfer:

```
₹20,000
```

Total money after transfer:

```
₹20,000
```

---

## 3. [[Isolation]]

Multiple transactions should not interfere with each other.

Each transaction should execute as if it is the only transaction running.

---

## 4. [[Durability]]

Once a transaction is committed, its changes are permanent, even if the system crashes immediately afterward.

---

## Transaction Control Commands (TCL)

Transaction Control Language (TCL) commands manage transactions in SQL.

---

### [[COMMIT]]

Permanently saves all changes.

Example:

```sql
COMMIT;
```

---

### [[ROLLBACK]]

Cancels all changes made during the current transaction.

Example:

```sql
ROLLBACK;
```

---

### [[SAVEPOINT]]

Creates a checkpoint inside a transaction.

Example:

```sql
SAVEPOINT sp1;
```

Rollback to a savepoint:

```sql
ROLLBACK TO sp1;
```

---

## Transaction Schedule

A **transaction schedule** is the order in which operations from one or more transactions are executed.

---

### Serial Schedule

Transactions execute one after another.

Example:

```text
T1 → T2 → T3
```

Advantages:

- No concurrency problems.
- Easy to maintain consistency.

Disadvantages:

- Slow.
- Poor resource utilization.

---

### Concurrent Schedule

Multiple transactions execute simultaneously.

Example:

```text
T1
T2
T3
```

Advantages:

- Faster execution.
- Better CPU utilization.
- Supports multiple users.

Disadvantages:

- May lead to concurrency problems if not controlled.

---

# Concurrency Control

Concurrency control ensures that simultaneous transactions do not produce inconsistent results.

---

## Common Problems

### [[Lost Update]]

Two transactions update the same data, causing one update to overwrite the other.

---

### [[Dirty Read]]

A transaction reads data modified by another transaction before it is committed.

---

### [[Non-Repeatable Read]]

A transaction reads the same row twice and gets different values because another transaction modified it.

---

### [[Phantom Read]]

A query executed twice returns different numbers of rows because another transaction inserted or deleted records.

---

## Concurrency Control Techniques

### [[Lock-Based Protocol]]

Uses locks to control access to data.

Types:

- Shared Lock (Read)
- Exclusive Lock (Write)

---

### [[Timestamp-Based Protocol]]

Orders transactions using timestamps.

Older transactions receive higher priority.

---

### [[Optimistic Concurrency Control]]

Assumes conflicts are rare.

Transactions execute freely and are validated before committing.

---

# Recovery Management

Recovery management restores the database after failures.

---

## Types of Failures

### Transaction Failure

A transaction fails because of logical or system errors.

---

### System Failure

Power failure or operating system crash.

---

### Media Failure

Disk crash or hardware failure.

---

## Recovery Techniques

### Log-Based Recovery

Stores every transaction in a log file.

Used for:

- Undo operations
- Redo operations

---

### Checkpoint

A checkpoint saves the current database state to reduce recovery time after a crash.

---

## Advantages of Transaction Processing

- Maintains data consistency.
- Prevents data corruption.
- Supports multiple users.
- Ensures reliable database operations.
- Provides automatic recovery.
- Maintains database integrity.

---

## Limitations

- Additional processing overhead.
- Complex concurrency management.
- Locking may reduce performance.
- Recovery mechanisms require extra storage.

---

## Applications

- Banking systems
- ATM transactions
- Online shopping
- Railway reservation systems
- Airline booking systems
- Hospital management systems
- Inventory management
- Payroll systems
- Financial applications

---

## ACID Properties Summary

| Property | Description |
|----------|-------------|
| [[Atomicity]] | All operations succeed or all fail |
| [[Consistency]] | Database remains valid before and after a transaction |
| [[Isolation]] | Concurrent transactions do not interfere with each other |
| [[Durability]] | Committed changes are permanent |

---

## Transaction States Summary

| State                         | Description                         |
| ----------------------------- | ----------------------------------- |
| [[Active State]]              | Transaction is executing            |
| [[Partially Committed State]] | Execution finished, awaiting commit |
| [[Committed State]]           | Changes permanently saved           |
| [[Failed State]]              | Transaction cannot continue         |
| [[Aborted State]]             | Transaction rolled back             |

---

## Serial vs Concurrent Schedule

| Serial Schedule | Concurrent Schedule |
|-----------------|---------------------|
| One transaction at a time | Multiple transactions simultaneously |
| Easy to maintain consistency | Higher performance |
| No concurrency problems | Requires concurrency control |
| Lower throughput | Better resource utilization |

---

## Real-World Examples

- Bank fund transfers
- Online ticket booking
- ATM withdrawals
- Online shopping checkout
- Hospital patient record updates
- Library management systems
- Payroll processing
- Inventory updates

---

## Related Notes

- [[Database Management System (DBMS)]]
- [[Database]]
- [[Transaction]]
- [[Transaction Processing]]
- [[ACID Properties]]
- [[Atomicity]]
- [[Consistency]]
- [[Isolation]]
- [[Durability]]
- [[COMMIT]]
- [[ROLLBACK]]
- [[SAVEPOINT]]
- [[Concurrency Control]]
- [[Lock-Based Protocol]]
- [[Timestamp-Based Protocol]]
- [[Optimistic Concurrency Control]]
- [[Lost Update]]
- [[Dirty Read]]
- [[Non-Repeatable Read]]
- [[Phantom Read]]
- [[Recovery Management]]
- [[Checkpoint]]
- [[Log-Based Recovery]]
- [[SQL]]