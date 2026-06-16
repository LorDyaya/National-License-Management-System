# Domain Relationships

## Overview

This document describes the main relationships between the domain entities and their business meanings.

---

## Person ↔ Driver

### Business Meaning

Extension

### Cardinality

Person (1) ↔ Driver (0..1)

### Description

A Driver is a specialization of a Person. A person becomes a driver after obtaining the first driving license.

---

## Person ↔ SystemUser

### Business Meaning

Extension

### Cardinality

Person (1) ↔ SystemUser (0..1)

### Description

A System User is a person who is authorized to access and operate the system.

---

## Person ↔ Application

### Business Meaning

Association

### Cardinality

Person (1) ↔ Applications (0..*)

### Description

A person can submit multiple applications during their lifetime in the system.

---

## Application ↔ License

### Business Meaning

Origin

### Cardinality

Application (1) ↔ License (0..1)

### Description

A license is issued as a result of a successful application.

---

## License ↔ LicenseClass

### Business Meaning

Association

### Cardinality

LicenseClass (1) ↔ Licenses (0..*)

### Description

Each license belongs to exactly one license class. A license class can be associated with many licenses.

---

## License ↔ LicenseHold

### Business Meaning

Lifecycle Event

### Cardinality

License (1) ↔ LicenseHolds (0..*)

### Description

A license may be held and released multiple times throughout its lifetime.

---

## Application ↔ Application

### Business Meaning

Recursive Dependency

### Cardinality

Application (1) ↔ Applications (0..*)

### Description

Retest applications reference an original application.

---

## TestType ↔ TestAttempt

### Business Meaning

Dependency

### Cardinality

TestType (1) ↔ TestAttempts (0..*)

### Description

A test attempt must be associated with a specific test type.

---

## TestAppointment ↔ TestAttempt

### Business Meaning

Workflow Dependency

### Cardinality

TestAppointment (1) ↔ TestAttempt (1)

### Description

Each appointment results in one test attempt.

---

## Application ↔ TestAppointment

### Business Meaning

Dependency

### Cardinality

Application (1) ↔ TestAppointments (0..*)

### Description

Test appointments are scheduled under a specific application.

---

## SystemUser ↔ Permission

### Business Meaning

Association

### Cardinality

SystemUser (0..*) ↔ Permission (0..*)

### Description

Users can be assigned multiple permissions and permissions can be assigned to multiple users.

