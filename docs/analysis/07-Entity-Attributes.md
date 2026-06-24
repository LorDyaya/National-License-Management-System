## Entity Attributes
Purpose

This document records the attributes discovered during the analysis phase 
for each domain entity in the National License Management System (NLMS).

The purpose of this document is to establish a stable domain baseline before moving to the Relational Schema and Physical
Database Design phases.

The attributes listed here represent the current understanding of the business domain and may evolve only when new 
requirements are discovered.

================================================
================================================

## person Entity
 PersonID
 NationalNumber
 FirstName
 SecondName
 ThirdName
 LastName
 DateOfBirth
 Nationality
 Address
 Phone
 Email
 ImagePath
 
=================
Notes :

- FullName is a composite attribute composed of:
FirstName
SecondName
ThirdName
LastName
- Age is a derived attribute and is calculated from DateOfBirth.
- NationalNumber is a business attribute and may be nullable according to the current business understanding.

================================================
================================================

## Driver Entity
DriverID
PersonID
DriverNumber
=================
Notes :

- Driver is a specialization of Person.
- DriverNumber is assigned once and remains unchanged

================================================
================================================

## User Entity
UserID
PersonID
Username
Password
IsFrozen  

================
Notes : 

- User is a specialization of Person.
- Password represents sensitive information.
- Username is required for authentication.

================================================
================================================

## Service Entity
ServiceID
ServiceName

================
Notes : 

- Represents a licensing service offered by the system.
- Financial information is analyzed separately.

================================================
================================================

## Application Entity
ApplicationID
ApplicationNumber
ApplicationPersonID
ServiceID
ApplicationDate
ApplicationStatus
PaidAppFee
ParentAppID

================
Notes : 

- ParentAppID supports the recursive relationship used for retest applications.
- ApplicationNumber is a business identifier.

================================================
================================================

## License Class Entity
LicenseClassID
ClassName
ClassDescription
MinimumAllowedAge
ValidityLength
ClassFees

================================================
================================================

## License Entity
LicenseID
LicenseNumber
DriverID
ApplicationID
LicenseClassID
IssueDate
ExpirationDate
Notes

================================================
================================================

## TestType Entity
TestTypeID
TestName

================================================
================================================

## License Class Test
LicenseClassID
TestTypeID
TestFee

================================================
================================================

## Test Appointment Entity
TestAppointmentID
ApplicationID
TestTypeID
UserID
AppointmentDate

================================================
================================================

## Test Attempt Entity
TestAttemptID
TestAppointmentID
TestDate
TestResult
Score

================
Notes : 

- Score may be nullable depending on the test type.

================================================
================================================

## User Permission Entity
UserID
PermissionID

================
Notes : 

- Represents the many-to-many relationship between User and Permission.

================================================
================================================

## AuditLog Entity
AuditLogID
UserID
ActionType
EntityName
RecordID
ActionDate

================================================
================================================

## License Hold Entity
LicenseHoldID
LicenseID
HoldDate
HoldReason
FineAmount
ReleaseDate

================
Notes :

- ReleaseDate is nullable because a hold may still be active.

================================================
================================================

## Service Test Requirement Entity
ServiceID
TestTypeID
Sequence

================
Notes :

- Defines which tests are required for a specific service and the order in which they must be completed.

================================================
================================================

Analysis Phase 'VR1' Completed 
Ready for Relational Schema Design
