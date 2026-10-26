# Lesson 5 Assessment
## Build & Validate a Production-Ready Employee Onboarding Automation

## 1. Assessment Overview

This assessment evaluates your ability to design, implement, test, and document a production-ready employee onboarding automation in n8n by integrating workflow orchestration, PostgreSQL data management, reusable sub-workflows, department-based routing, manager approval, asynchronous waiting, and operational error handling into one capstone solution.

You will build a modular onboarding platform consisting of a master onboarding orchestrator, IT and HR provisioning workers, and a global error-handling workflow. The solution must prevent duplicate employee creation, create employee and onboarding records, invoke reusable worker workflows, request approval in Slack, pause for a webhook response or timeout, update approval state, and provide complete validation and deployment evidence.

## 2. Assessment Objective

Demonstrate your ability to build a complete production-ready employee onboarding automation that follows enterprise workflow design practices. The final solution should integrate PostgreSQL, duplicate validation, employee profile creation, department routing, reusable IT and HR provisioning sub-workflows, Slack approval notifications, Wait-node webhook resumption, approval status updates, testing with cURL, operational documentation, and production-readiness validation.

## 3. Prerequisites

- Review the Topic 15 assessment material and the employee onboarding workflow requirements before starting.
- Prepare an n8n environment hosted through Docker Compose, Kubernetes, or another suitable runtime.
- Configure PostgreSQL, Slack credentials, webhook access, and the required n8n credentials securely.
- Create or review the capstone_employees and capstone_onboarding_tasks database schema before workflow implementation.
- Have a GitHub account available for public source submission and a tool such as cURL for webhook validation.

## 4. Assessment Tasks

### Exercise 1 – Build the Production Onboarding Architecture

Design the complete modular architecture using Pipeline A as the Master Onboarding Orchestrator, Pipeline B as the IT Provision Worker, Pipeline C as the HR Provision Worker, and Pipeline D as the Global Error Logger. Configure the infrastructure dependencies, webhook ingress, secure credentials, PostgreSQL connectivity, and workflow relationships required for production execution.

### Exercise 2 – Implement Database Validation and Employee Profile Creation

Configure PostgreSQL integration for employee and onboarding-task management. Implement duplicate validation by email using SQL_CheckDuplicates, stop duplicate onboarding requests, and create the employee profile plus onboarding checklist with SQL_CreateProfile. Validate the employee_id, department, and role values returned for downstream workflow routing.

### Exercise 3 – Build Department Routing and Reusable Provisioning Workers

Configure Route_Department to send Engineering employees to the IT Provision Worker and HR/Marketing employees to the HR Provision Worker. Use Execute Workflow nodes to pass employee_id, department, and role into child workflows. Implement the IT worker to simulate GitHub provisioning and update it_provisioned, and implement the HR worker to simulate payroll setup and update hr_payroll_setup.

### Exercise 4 – Implement Slack Approval, Asynchronous Waiting, and Status Updates

Send a Slack approval notification containing employee name, department, role, and approval requirement. Configure a Wait node to resume by webhook using the capstone-approval-response path with a two-hour timeout. Process the approval callback and update approval_status to approved in PostgreSQL using the employee_id.

### Exercise 5 – Test, Document, Validate, and Submit the Capstone

Apply production naming standards and workflow annotations, link the global error-handling workflow, execute webhook-based tests using cURL, validate database updates and successful end-to-end execution, capture evidence, export Pipelines A, B, and C as n8n workflow JSON files, and prepare the complete LMS submission package including documentation, demo video, repository, SQL scripts, screenshots, and deployment instructions.

## 5. Practical Assessment Checklist

- [ ] Infrastructure Configured
- [ ] PostgreSQL Database Schema Created
- [ ] Webhook Trigger Configured
- [ ] Duplicate Validation Implemented
- [ ] Employee Profile and Onboarding Checklist Created
- [ ] Department Routing Configured
- [ ] IT Provision Worker Built
- [ ] HR Provision Worker Built
- [ ] Execute Workflow Nodes Configured
- [ ] Slack Approval Notification Configured
- [ ] Wait Node and Webhook Resume Implemented
- [ ] Approval Status Updated in PostgreSQL
- [ ] Global Error Handling Linked
- [ ] Workflow Documentation and Naming Standards Applied
- [ ] SQL Queries Validated
- [ ] cURL Testing Completed
- [ ] Production Readiness Checklist Completed
- [ ] Workflow JSON Exports Prepared
- [ ] Source Repository Ready for Submission

## 6. Assessment Success Criteria

- Design a modular employee onboarding architecture using parent and child workflows.
- Configure PostgreSQL for employee and onboarding-task management.
- Prevent duplicate employee creation through database validation.
- Create employee profiles and onboarding checklist records successfully.
- Route employees dynamically based on department.
- Implement reusable IT and HR provisioning sub-workflows.
- Pass employee context correctly between the master and worker workflows.
- Configure Slack notifications for manager approval.
- Use the Wait node for asynchronous webhook-based approval handling.
- Update approval status in PostgreSQL after approval.
- Apply production-ready naming, documentation, and error-handling practices.
- Test the complete onboarding process with webhook requests and validate database changes.
- Submit all mandatory LMS assessment deliverables.

## 7. Required Deliverables

- Loom/YouTube Video Link — Mandatory
- GitHub Public Repository — Mandatory
- Documentation Package (PDF/DOCX) — Mandatory
- Exported n8n Workflow JSON Files – Pipelines A, B, and C — Mandatory
- SQL Initialization / Schema Scripts — Mandatory
- Workflow Testing Evidence / Screenshots — Mandatory
- cURL Validation Commands — Mandatory
- Deployment and Setup Instructions — Mandatory
- Description / Additional Comments — Recommended

## 8. Submission Guidelines

- A Loom or YouTube video demonstrating webhook execution, duplicate validation, employee creation, department routing, IT and HR sub-workflow execution, Slack approval notification, Wait-node behavior, approval callback handling, and PostgreSQL updates.
- A public GitHub repository containing the exported n8n workflow JSON files for Pipelines A, B, and C, SQL initialization/schema scripts, documentation files, testing screenshots, cURL validation commands, and deployment/setup instructions.
- A PDF or DOCX documentation package containing the Workflow Architecture Diagram, Infrastructure Setup, Database Schema, Parent Workflow Documentation, IT Provision Workflow Documentation, HR Provision Workflow Documentation, SQL Query Documentation, Node Configuration Blueprint, Testing Evidence, and Production Readiness Checklist.
- In the Description field, document any challenges faced, how they were resolved, assumptions made, known limitations, additional features implemented, or comments for the assessor.

## 9. Final Submission Checklist

- [ ] Completed all assessment exercises
- [ ] Verified webhook-based onboarding execution
- [ ] Verified duplicate validation behavior
- [ ] Verified employee profile and checklist creation
- [ ] Verified department routing
- [ ] Verified IT and HR worker execution
- [ ] Verified Slack approval notification
- [ ] Verified Wait-node resume and timeout behavior
- [ ] Verified PostgreSQL approval status updates
- [ ] Validated SQL queries and database records
- [ ] Completed cURL-based testing
- [ ] Exported Pipelines A, B, and C as n8n workflow JSON files
- [ ] Pushed the latest source files and documentation to GitHub
- [ ] Verified the GitHub repository is public and accessible
- [ ] Uploaded the Loom/YouTube demonstration video
- [ ] Included SQL scripts, screenshots, and deployment/setup instructions
- [ ] Reviewed all deliverables before submission

In the Description field, include relevant challenges, resolutions, assumptions, limitations, enhancements, or assessor notes.

## 10. Important Note

- A Loom or YouTube video link demonstrating the complete employee onboarding automation and all major workflow stages.
- A public GitHub repository containing the exported n8n workflow JSON files for Pipelines A, B, and C, SQL initialization scripts, documentation, testing screenshots, cURL commands, and deployment/setup instructions.
- A complete PDF/DOCX documentation package covering architecture, infrastructure, database schema, parent and worker workflows, SQL queries, testing evidence, and production readiness.
- Additional comments describing challenges, resolutions, assumptions, limitations, or improvements where applicable.

Before clicking Submit in the LMS, ensure that you have provided:

Submissions without the required video demonstration, accessible source repository, workflow exports, SQL scripts, or mandatory documentation may be considered incomplete and may not be evaluated.
