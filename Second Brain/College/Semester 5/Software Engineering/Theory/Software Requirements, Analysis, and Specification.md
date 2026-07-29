# Software Requirements, Analysis, and Specification

**Tags:** [[Software Engineering]] [[Software Requirements]] [[Requirement Analysis]] [[Software Requirement Specification]] [[Requirement Engineering]] [[Requirement Engineering Lifecycle]] [[Requirement Elicitation]] [[Requirement Analysis]] [[Requirement Prioritization]] [[Requirement Validation]] [[Requirement Traceability]] [[Requirement Traceability Matrix]] [[Change Management]] [[Informal Specification]] [[Formal Specification]] [[Functional Requirements]] [[Non-Functional Requirements]] [[Stakeholders]]

---

# Introduction

[[Software Requirements]] define **what a software system should do** and the constraints under which it must operate. Requirements form the foundation of every software project, as they guide design, development, testing, and maintenance.

Incorrect or incomplete requirements often lead to:

- Project delays
    
- Increased development costs
    
- Software defects
    
- Customer dissatisfaction
    
- Project failure
    

Requirement Engineering ensures that software requirements are **accurate, complete, consistent, feasible, and verifiable**.

---

# What is a Software Requirement?

A [[Software Requirement]] is a documented need or condition that a software system must satisfy.

It describes:

- Features the system should provide
    
- Services it must perform
    
- Performance expectations
    
- Security requirements
    
- User interactions
    
- Business rules
    

Example:

> "The system shall allow users to log in using an email address and password."

---

# Types of Software Requirements

Software requirements are generally classified into two categories.

---

# Functional Requirements

[[Functional Requirements]] describe **what the software should do**.

They specify the functions and services provided by the system.

Examples:

- User registration
    
- Login authentication
    
- Password reset
    
- Online payment
    
- Report generation
    
- Search functionality
    

Example:

```text
The system shall allow users
to upload profile pictures.
```

---

# Non-Functional Requirements

[[Non-Functional Requirements]] describe **how well the software should perform**.

They define quality attributes rather than specific functions.

Examples:

- Performance
    
- Reliability
    
- Security
    
- Scalability
    
- Availability
    
- Usability
    
- Maintainability
    

Example:

```text
The system shall respond
within 2 seconds.
```

---

# Requirement Analysis

[[Requirement Analysis]] is the process of examining, refining, organizing, and validating requirements to ensure they correctly represent stakeholder needs.

Objectives include:

- Remove ambiguity
    
- Identify conflicts
    
- Ensure completeness
    
- Verify feasibility
    
- Improve requirement quality
    

Requirement analysis acts as a bridge between stakeholders and developers.

---

# Requirement Specification

[[Software Requirement Specification]] (SRS) is a formal document describing all functional and non-functional requirements of a software system.

The SRS serves as a contract between customers and developers.

An SRS typically contains:

- Introduction
    
- System overview
    
- Functional requirements
    
- Non-functional requirements
    
- Constraints
    
- Assumptions
    
- Acceptance criteria
    

Benefits:

- Reduces misunderstandings
    
- Supports testing
    
- Simplifies maintenance
    
- Improves communication
    

---

# Informal Specification

[[Informal Specification]] describes requirements using **natural language**.

It is the simplest method of documenting requirements.

Example:

```text
The system should allow
students to register for courses.
```

---

## Advantages

- Easy to write
    
- Easy to understand
    
- Suitable for discussions with stakeholders
    
- No specialized knowledge required
    

---

## Disadvantages

- Ambiguous
    
- Can be misunderstood
    
- Difficult to verify
    
- May contain inconsistencies
    

---

# Formal Specification

[[Formal Specification]] describes requirements using **mathematical notation or formal languages**.

Formal methods eliminate ambiguity by expressing system behavior precisely.

Examples of formal specification languages:

- Z Notation
    
- VDM (Vienna Development Method)
    
- B-Method
    
- Alloy
    

Example (conceptual):

```text
Login(User, Password)

↓

Authenticated User
```

Unlike informal specifications, formal specifications have precise syntax and semantics.

---

## Advantages

- Unambiguous
    
- Precise
    
- Easier verification
    
- Supports formal proof of correctness
    
- Suitable for safety-critical systems
    

---

## Disadvantages

- Difficult to learn
    
- Time-consuming
    
- Requires specialized expertise
    
- Less suitable for small projects
    

---

# Informal vs Formal Specification

|Feature|Informal Specification|Formal Specification|
|---|---|---|
|Language|Natural Language|Mathematical Notation|
|Ease of Writing|Easy|Difficult|
|Ambiguity|High|Very Low|
|Verification|Difficult|Easier|
|Best For|Small Projects|Critical Systems|

---

# Requirement Engineering

[[Requirement Engineering]] is the systematic process of discovering, documenting, validating, and managing software requirements throughout the project lifecycle.

It ensures that the final software satisfies stakeholder expectations.

---

# Requirement Engineering Lifecycle

The Requirement Engineering Lifecycle consists of several sequential activities.

```text
Requirement Elicitation
          ↓
Requirement Analysis
          ↓
Requirement Prioritization
          ↓
Requirement Validation
          ↓
Requirement Management
```

---

# Requirement Elicitation

[[Requirement Elicitation]] is the process of collecting requirements from stakeholders.

Stakeholders include:

- Customers
    
- End users
    
- Managers
    
- Domain experts
    
- Developers
    

---

## Requirement Elicitation Techniques

### Interviews

One-on-one discussions with stakeholders.

Advantages:

- Detailed information
    
- Clarification possible
    

---

### Questionnaires

Used when many stakeholders are involved.

Advantages:

- Cost-effective
    
- Fast
    

---

### Workshops

Group meetings where stakeholders discuss requirements collaboratively.

---

### Observation

Analysts observe users performing actual tasks.

Useful for understanding existing workflows.

---

### Brainstorming

Generates new ideas through group discussion.

---

### Prototyping

Creates an early version of the software to gather feedback.

---

# Requirement Analysis

After gathering requirements, they must be analyzed.

Activities include:

- Identifying inconsistencies
    
- Removing duplicate requirements
    
- Resolving conflicts
    
- Checking feasibility
    
- Organizing requirements
    

Output:

A refined and structured set of requirements.

---

# Requirement Prioritization

[[Requirement Prioritization]] determines the order in which requirements should be implemented.

Since resources are limited, not all requirements can be completed immediately.

---

## Common Prioritization Methods

### MoSCoW Technique

Requirements are classified as:

- Must Have
    
- Should Have
    
- Could Have
    
- Won't Have (for now)
    

---

### Value-Based Prioritization

Requirements providing higher business value are implemented first.

---

### Risk-Based Prioritization

High-risk requirements are developed earlier to reduce project uncertainty.

---

# Benefits

- Better resource allocation
    
- Faster delivery
    
- Improved customer satisfaction
    
- Reduced project risk
    

---

# Requirement Validation

[[Requirement Validation]] ensures that documented requirements accurately represent stakeholder needs.

It answers the question:

> **"Are we building the right software?"**

Validation checks:

- Correctness
    
- Completeness
    
- Consistency
    
- Feasibility
    
- Testability
    

---

## Validation Techniques

- Requirement reviews
    
- Inspections
    
- Walkthroughs
    
- Prototyping
    
- Acceptance criteria verification
    

---

# Requirement Management

Requirements often change during software development.

Requirement Management ensures that changes are documented, evaluated, approved, and communicated.

Activities include:

- Recording changes
    
- Version control
    
- Impact analysis
    
- Requirement traceability
    
- Change approval
    

---

# Requirement Traceability

[[Requirement Traceability]] is the ability to track each requirement throughout the software development lifecycle.

Traceability connects requirements with:

- Design documents
    
- Source code
    
- Test cases
    
- User stories
    
- Change requests
    

This ensures that every requirement is implemented and tested.

---

# Types of Requirement Traceability

### Forward Traceability

Tracks requirements from specification to implementation and testing.

```text
Requirement

↓

Design

↓

Code

↓

Test Case
```

---

### Backward Traceability

Tracks completed system components back to their original requirements.

Ensures that every implemented feature has a valid requirement.

---

### Bidirectional Traceability

Combines both forward and backward traceability.

Provides complete visibility throughout the project.

---

# Requirement Traceability Matrix (RTM)

A [[Requirement Traceability Matrix]] (RTM) is a document that maps each requirement to its corresponding design, implementation, and testing artifacts.

The RTM helps ensure that:

- Every requirement is implemented.
    
- Every requirement is tested.
    
- No unnecessary features are developed.
    
- Changes can be tracked efficiently.
    

---

## Example RTM

|Requirement ID|Requirement|Design Module|Test Case|Status|
|---|---|---|---|---|
|R1|User Login|Authentication|TC01|Completed|
|R2|Password Reset|User Module|TC02|Completed|
|R3|Payment Gateway|Payment Module|TC03|In Progress|

---

## Benefits of RTM

- Complete requirement coverage
    
- Easier testing
    
- Better project tracking
    
- Simplified audits
    
- Improved quality assurance
    
- Easier maintenance
    

---

# Change Management

[[Change Management]] is the process of handling modifications to software requirements in a controlled manner.

Changes may occur because of:

- Customer requests
    
- Business policy updates
    
- Legal requirements
    
- Technology changes
    
- Bug fixes
    
- Market demands
    

Without proper change management, software projects may experience delays, cost overruns, and inconsistent implementations.

---

# Change Management Process

```text
Change Request
       ↓
Impact Analysis
       ↓
Approval
       ↓
Implementation
       ↓
Testing
       ↓
Update Documentation
```

---

## Impact Analysis

Before approving a change, the team evaluates:

- Cost
    
- Time
    
- Risks
    
- Affected modules
    
- Required resources
    

This helps determine whether the proposed change is feasible.

---

# Importance of Change Management

- Prevents uncontrolled changes
    
- Improves software quality
    
- Reduces project risks
    
- Maintains documentation consistency
    
- Supports requirement traceability
    
- Facilitates teamwork
    

---

# Relationship Between Requirement Engineering and SDLC

Requirement Engineering is the first and one of the most critical phases of the [[Software Development Life Cycle]].

The quality of requirements directly influences:

- System design
    
- Development
    
- Testing
    
- Deployment
    
- Maintenance
    

Poor requirements often lead to poor software quality.

---

# Real-World Applications

## Banking Systems

Requirements define secure authentication, transaction processing, and regulatory compliance.

---

## E-Commerce Platforms

Requirement traceability ensures features such as shopping carts, payments, and order tracking are fully implemented and tested.

---

## Healthcare Systems

Formal specifications and traceability help ensure patient safety and regulatory compliance.

---

## Aviation and Defense

Formal specification methods are widely used to build highly reliable, safety-critical systems.

---

# Advantages of Requirement Engineering

- Reduces development errors
    
- Improves communication
    
- Ensures customer satisfaction
    
- Simplifies testing
    
- Supports project planning
    
- Improves software quality
    

---

# Limitations

- Time-consuming
    
- Requires active stakeholder participation
    
- Frequent requirement changes can increase project cost
    
- Formal specifications require specialized expertise
    

---

# Summary

[[Requirement Engineering]] is the systematic process of identifying, documenting, analyzing, validating, and managing software requirements. It begins with [[Requirement Elicitation]], followed by [[Requirement Analysis]], [[Requirement Prioritization]], and [[Requirement Validation]], ensuring that stakeholder needs are accurately captured and translated into software requirements.

Requirements may be documented using [[Informal Specification]] or [[Formal Specification]], depending on project complexity. Effective [[Requirement Traceability]] through a [[Requirement Traceability Matrix]] (RTM) ensures every requirement is linked to design, implementation, and testing, while [[Change Management]] controls requirement modifications throughout the project lifecycle, improving software quality and reducing project risks.

---

# Key Terms

- [[Software Engineering]]
    
- [[Software Requirements]]
    
- [[Requirement Analysis]]
    
- [[Software Requirement Specification]]
    
- [[Software Requirement Specification (SRS)]]
    
- [[Requirement Engineering]]
    
- [[Requirement Engineering Lifecycle]]
    
- [[Requirement Elicitation]]
    
- [[Requirement Prioritization]]
    
- [[Requirement Validation]]
    
- [[Requirement Management]]
    
- [[Requirement Traceability]]
    
- [[Requirement Traceability Matrix]]
    
- [[Change Management]]
    
- [[Functional Requirements]]
    
- [[Non-Functional Requirements]]
    
- [[Informal Specification]]
    
- [[Formal Specification]]
    
- [[Stakeholders]]
    
- [[MoSCoW Technique]]
    
- [[Impact Analysis]]