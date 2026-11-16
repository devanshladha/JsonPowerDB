# Student Enrollment Form

A small browser-based student enrollment form that demonstrates storing student records in JsonPowerDB. The form is implemented in a single HTML file and targets the `SCHOOL-DB` database and `STUDENT-TABLE` relation.

## Table of Contents

- [Description](#description)
- [Scope of Functionalities](#scope-of-functionalities)
- [Database Setup](#database-setup)
- [Benefits of Using JsonPowerDB](#benefits-of-using-jsonpowerdb)
- [Project Status](#project-status)
- [Release History](#release-history)
- [Sources](#sources)

## Description

The form stores these student fields:

| Field | Description |
| --- | --- |
| `Roll-No` | Student identifier and relation key |
| `Full-Name` | Student's full name |
| `Class` | Student's class or grade |
| `Birth-Date` | Student's date of birth |
| `Address` | Student's address |
| `Enrollment-Date` | Date the student enrolled |

The project uses the JsonPowerDB HTTP API to look up, insert, and update records. The user interface and client-side logic are in [`index.html`](index.html).

## Scope of Functionalities

- Starts with an empty form, focused on `Roll-No`; detail fields and action buttons are disabled.
- Looks up a record after a Roll No. is entered.
- Enables the detail fields and Save/Reset for a new Roll No.
- Loads an existing student's details, locks the Roll No., and enables Update/Reset.
- Checks that all fields are filled before sending a write request.
- Resets the form after a successful operation.

## Database Setup

1. Configure a JsonPowerDB database named `SCHOOL-DB` and a relation named `STUDENT-TABLE`.
2. Configure `Roll-No` as the relation's key/index used for lookups.
3. In `index.html`, configure the database URL, database name, relation name, and a valid connection token for your JsonPowerDB instance.
4. Open `index.html` in a modern browser. The browser needs network access to the JsonPowerDB API, and the API must allow requests from the page's origin.

> [!WARNING]
> A connection token embedded in browser JavaScript is visible to anyone who can access the page. Use a disposable development token for this demo. A production deployment should send database requests through a server-side component that protects credentials.

## Benefits of Using JsonPowerDB

- JSON request and response data makes it convenient to work with JavaScript applications.
- Its API-based design provides database operations without requiring a database driver in this page.
- JsonPowerDB supports multiple data models, including document, relational, key-value, geospatial, and time-series use cases.
- Its schema-flexible JSON storage can make it easier to evolve a project as its data fields change.

See the [JsonPowerDB documentation](https://login2explore.com/jpdb/docs.html) for supported commands and configuration details.
