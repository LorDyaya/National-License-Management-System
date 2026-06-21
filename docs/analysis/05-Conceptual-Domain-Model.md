# Conceptual Domain Model

## Purpose

The purpose of this conceptual domain model is to provide a high-level, business-oriented view of the Driving License Management System.

This model focuses on explaining the main business concepts and the primary journey within the system without introducing technical implementation details. It is intended to help both technical and non-technical stakeholders understand how the system works and what business problem it solves.

The model illustrates the core journey of a person applying for a driving license, progressing through the required testing process, and eventually becoming a legally licensed driver.

---

## Business Story

In this system, a person wants to become a legally licensed driver.

To achieve this goal, the person submits an application for a driving license. The applicant must then progress through the required testing process and successfully pass all mandatory requirements.

Once the testing requirements are completed successfully, the person becomes eligible to obtain a driving license and is recognized by the system as a driver.

---

## Abstraction Level

This conceptual model intentionally presents a simplified view of the domain.

The goal of this model is to communicate the main business journey and core concepts rather than every business detail discovered during the analysis phase.

Several concepts are intentionally hidden behind higher-level abstractions. For example, the concept of "Test Progress" represents multiple detailed concepts such as test types, test appointments, test attempts, and the retest process.

These concepts remain part of the domain and will appear in later, more detailed models. However, they are intentionally abstracted at this stage to keep the model focused, understandable, and accessible to both technical and non-technical stakeholders.

---

## Core Concepts

The first version of the conceptual model focuses on the following core business concepts:

* Person
* Application
* Test Progress
* License
* License Class
* Driver

---

## Conceptual Model (Version 1)

```text
Driver
  △
  │
Person ───► Application ───► Test Progress ───► License
                                                        │
                                                        ▼
                                                  LicenseClass
```

---

## Scope

This model focuses only on the primary business journey of obtaining a driving license.

Administrative concepts such as system users, permissions, license holds, and other supporting operational features are intentionally excluded from this version and may appear in future conceptual or detailed domain models.

---

## Notes

This model is intended to communicate business understanding rather than technical design.

Cardinality, database structures, implementation details, and technical constraints are intentionally omitted and will be introduced in later modeling stages.

==========================================================================
==========================================================================

## Conceptual Model (Version 2)

As the domain analysis progressed, additional business concepts emerged that refined the understanding of the licensing process.

The original conceptual model intentionally represented several complex processes as higher-level abstractions. During the detailed analysis phase, these abstractions were decomposed into more specialized concepts.

In particular, the concept of **Test Progress** was discovered to be a richer sub-domain composed of multiple business concepts, including:

* Test Types
* Test Appointments
* Test Attempts
* Retest Applications

Similarly, the licensing process revealed additional concepts that are important to the business domain, such as:

* License Classes
* License Hold History
* Driver Recognition

These concepts remain part of the same business journey but provide a more detailed and accurate understanding of how the system operates.

The refined conceptual journey can be viewed as:

```text
Person
   │
   ▼
Application
   │
   ▼
Testing Process
   │
   ▼
License
   │
   ▼
Driver
```

Where:

* **Testing Process** represents the complete journey of scheduling, attempting, and potentially retaking the required tests.
* **License** represents the successful outcome of completing all business requirements.
* **Driver** represents the business transition of a person becoming an officially licensed driver in the system.

=====================================================================================
=====================================================================================

## Evolution of the Conceptual Understanding

The conceptual model evolved throughout the analysis process.

The first version focused on communicating the main business story in a simple and accessible manner for both technical and non-technical stakeholders.

As the analysis became more detailed, additional concepts and business rules were discovered. Rather than replacing the original conceptual model, these discoveries refined and enriched the understanding of the domain.

This iterative evolution reflects the nature of domain analysis, where understanding deepens progressively as more business rules and requirements are explored.

The conceptual model therefore serves as a bridge between:

* Business Understanding
* Detailed Domain Analysis
* Logical and Physical System Design

The subsequent models will introduce more detailed representations of the domain, including entities, relationships, cardinalities, and implementation-oriented concerns.
