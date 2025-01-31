# Technical Specification

## Elmentor Program

### 1. Environment Overview

The Elmentor Program operates within a structured and scalable technological environment designed for high availability, security, and automation. The core components include:

- **Microsoft Azure Cloud** as the primary hosting and infrastructure environment.
- **Microsoft Teams** for communication, collaboration, and member engagement.
- **WordPress** for content management, user authentication, and course administration.
- **Question-to-Answer Platform** for knowledge sharing and structured Q&A interactions.
- **GitHub Private Repositories** for version control, automation scripts, and infrastructure management.

### 2. Member Registration Process

#### 2.1 Registration Workflow

1. **Data Collection:** Members initiate registration by filling out a Microsoft Form.
2. **Data Processing:** Submitted data is downloaded and utilized throughout the registration process.
3. **Azure Tenant Integration:** Members are added as guest accounts on the Azure Tenant.
4. **WordPress Registration:**
   - Members are assigned specific roles and memberships based on their subscription type.
   - Integration with the Membership plugin ensures access control and authentication.
   - If applicable, members are enrolled in Learning Management System (LMS) courses.
5. **Question-to-Answer Platform Registration:**
   - Members gain access based on their roles.
6. **Microsoft Teams Integration:**
   - Members are added to multiple Teams channels (approximately 90 channels).
   - Tags are assigned based on membership and subscription type.
   - Members are also included in 35-40 distribution lists and groups.
7. **Database Management:**
   - All member details, including names, specializations, experiences, and subscription data, are stored in an SQL Server database hosted in Azure Cloud.
   - Historical tracking is maintained using a `MemberHistory` table to log changes (e.g., phone number updates).

### 3. File System Interactor

A modular component designed to read and write data to the file system with:

- **Excel file handling** for member data processing.
- **Markdown profile generation** using structured templates.
- **Interaction with automation scripts** for seamless data exchange.

### 4. Markdown Handler

A specialized component to format and generate structured Markdown output:

- **Utilizes predefined templates** to ensure consistency.
- **Integrates with the File System Interactor** for writing and retrieving Markdown files.
- **Supports future extensions,** such as API-based formatting.

### 5. Automation Toolkits

To enhance operational efficiency, multiple automation toolkits are deployed:

#### 5.1 WordPress Automation Toolkit
- User management, including creation, role assignments, and course enrollments.
- Automated compliance quiz enrollments.
- Uses **Playwright** for UI automation.

#### 5.2 Question-to-Answer Automation Toolkit
- Automated member registration and management.
- UI automation via **Playwright**.

#### 5.3 M365 Toolkit for Microsoft Teams
- Member onboarding/offboarding.
- Sending templated messages (e.g., onboarding welcome, reminders, announcements).
- Tagging automation for Teams channels.

#### 5.4 Azure Automation Toolkit
- Automated guest user onboarding to Azure.
- Role-based access management.

#### 5.5 Orchestrator CLI
- Centralized execution for Azure, WordPress, and Question-to-Answer commands.
- Ensures silent and efficient background execution of automation tasks.

### 6. Design Principles

- **High Reusability & Modularity:** Each component is designed to be reused and extended.
- **Abstraction:** Components avoid tight dependencies, allowing future technology swaps (e.g., replacing Playwright with API-based automation).
- **Scalability:** Components are structured for future API exposure.

### 7. Testing Strategy

A robust integration and end-to-end testing framework ensures system stability:

- **Verification of all transactions** (e.g., user registration, data consistency, automation execution).
- **Pre and post-condition comparisons** to validate state changes.
- **Reporting and tracking** for debugging and auditability.

### 8. Automation and CI/CD

To maintain continuous integration and deployment, the following practices are implemented:

#### CI/CD Pipelines:
- Automated package builds and deployments via **GitHub Packages**.
- Versioned releases for toolkits.

#### GitHub Actions Reusability:
- Standardized workflows ensure reusability across different repositories.

#### Testing Environments:
- Automated provisioning of isolated testing environments for **WordPress** and **Question-to-Answer platforms**.

#### Pre-Production Staging:
- Dedicated **pre-production environments** for validation before deployment.
- **Data masking techniques** to anonymize production data.

### 9. Command Line Tools

Each command-line interface (CLI) follows a structured documentation approach:

#### `--help` Feature:
- Provides **detailed parameter descriptions, usage instructions, and examples**.

#### XML Documentation:
- Embedded in code to facilitate **auto-generated documentation**.

#### Docs as Code:
- CLI documentation is published using a structured **Docs as Code** model, similar to **GitHub Docs** and **Microsoft Docs**.

### 10. Best Practices

To ensure consistency and maintainability, the best practices in n common conventions and standards doc are enforced:

- **Standardized Release Notes:** Every release includes structured documentation.
- **Structured GitHub Stories:** Feature development follows clear and detailed issue tracking.
- **Naming Conventions:**
  - `kebab-case` 
  - `PascalCase` 
  - `camelCase` 
  - Etc.

### 11. Conclusion

The Elmentor Program leverages a highly automated, modular, and scalable system for community management. With strong testing, automation, and best practices, it ensures efficiency, flexibility, and a seamless user experience.
