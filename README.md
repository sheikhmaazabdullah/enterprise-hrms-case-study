# Enterprise HRMS — Architecture Case Study

> A case study of the enterprise HRMS SaaS platform I work on as a Full Stack Developer at Softrack Technologies, Karachi (since September 2023). This repository documents architecture and engineering decisions at a general level only — it contains **no proprietary code, no database schemas, no client names and no client data**.

## The system

A multi-tenant, browser-based Human Resource Management System used by enterprise clients in the pharmaceutical, manufacturing, food processing and travel sectors. One deployment serves an entire client organisation through two portals:

- **Admin portal** — HR and management teams
- **Employee Self-Service (ESS) portal** — every employee

### Modules (30+)

Payroll · Income Tax · Overtime · Leave Management · Time & Attendance · Recruitment · Performance Appraisal · Loans · Asset Management · plus supporting administration, reporting and configuration modules.

## My role

- Development, testing and maintenance of the platform (PHP / Laravel, JavaScript)
- Owner of the **payroll processing workflow**
- Responsible for **Role-Based Access Control (RBAC)** across both portals
- Database work: schema design, stored procedures, triggers, indexing, query optimisation (Microsoft SQL Server, Oracle)
- Analytical dashboards and management reports (HR KPIs, headcount trends, service-ticket resolution)
- Client-facing: requirement-gathering, customisation and technical support
- Part of the phased migration of legacy Classic ASP applications to a .NET architecture

## Result I'm most proud of: payroll close, 3 days → under 4 hours

**Problem.** The monthly payroll close — statutory deductions, bonuses, loan adjustments and overtime computation across a full workforce — took approximately three working days of processing and checking.

**Approach.** Rebuilt the calculation path as an automated Laravel payroll/tax engine: rules expressed as data and code paths that could be re-run safely, with the workflow sequenced so attendance, leave, loans and overtime feed payroll instead of being reconciled by hand.

**Result.** The monthly payroll close cycle dropped from ~3 working days to **under 4 hours**, and the workflow is now the standard path for client payroll runs.

## Access control at scale

The Admin and ESS portals serve **300+ concurrent users per client deployment**, with data access scoped by role — an employee sees their own record, a manager sees their team, HR sees their organisation, and no tenant ever sees another tenant's data. Getting RBAC right in a multi-tenant HR system is less about login screens and more about enforcing scope on every query and report, which is where most of the design care went.

## Reporting

Management dashboards surface the numbers HR leadership actually asks for: headcount trends, HR KPIs, and service-ticket resolution metrics — generated from the same transactional data the modules produce, not from side spreadsheets.

## Working method

Agile/Scrum SDLC end to end: requirement analysis → technical specification → development → code review → unit testing → deployment → post-deployment support, in direct contact with the client organisations using the system.

## Tech

PHP (Core & OOP) · Laravel · JavaScript (ES6+) · jQuery · Bootstrap · Microsoft SQL Server · Oracle · RESTful APIs · MVC · RBAC · Multi-tenant SaaS architecture · Git

---

*Sheikh Maaz Abdullah — Full Stack Developer, Karachi · sheikhmaazabdullah@gmail.com · [LinkedIn](https://www.linkedin.com/in/sheikhmaazabdullah/)*
