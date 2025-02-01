# Technical Specification

## Elmentor Program

### 1. Introduction

The **Elmentor Program** is a **private community** aimed at **knowledge sharing and continuous development** among its members. It focuses on **technical skills, soft skills, leadership skills, mental health, mindset shifts, and cognitive development**. To build an environment that fosters these areas, members need to **engage with one another through meetings, events, and collaborative activities**.

To support these interactions effectively, we utilize the following **environments and platforms**, each serving a specific purpose:

### 2. Environment Overview

#### Microsoft Azure Cloud

- **Purpose:** Serves as the primary hosting and infrastructure environment.
- **Usage:** Supports the backend, databases, and cloud-based services required for community operations.

#### Microsoft Teams

- **Purpose:** Facilitates **communication and collaboration** among members.
- **Usage:** Used for **meetings, discussions, group collaborations, and structured engagement**.

#### WordPress

- **Purpose:** Provides **session and course viewing and management**.
- **Usage:** Hosts **learning materials, recorded sessions, and structured training programs**.

#### Question-to-Answer Platform

- **Purpose:** Enables **knowledge sharing and structured Q&A interactions**.
- **Usage:** Allows members to **ask and answer questions, discuss technical challenges, and share expertise**.

#### GitHub Private Repositories

- **Purpose:** Supports **user profile management and asset management**.
- **Usage:** Used to **store reusable assets**, templates, reusable assets and resources for members.

### 3. Member Registration Process

#### 3.1 Registration Workflow

1. **Data Collection:** Members initiate registration by filling out a **Microsoft Form**.
2. **Data Processing:** Submitted data is downloaded and utilized throughout the registration process.
3. **Azure Tenant Integration:** Members are added as **guest accounts** on the **Azure Tenant**.
4. **WordPress Registration:**
    - Members are assigned specific **roles** and memberships based on their subscription type.
    - Integration with the **Membership plugin** ensures access control and authentication.
    - If applicable, members are enrolled in **Learning Management System (LMS) courses**.
5. **Question-to-Answer Platform Registration:**
    - Members are added to the platform and granted access based on their roles.
6. **Microsoft Teams Integration:**
    - Members are added to **multiple Teams channels** (approximately 90 channels).
    - **Tags** are assigned based on membership and subscription type.
    - Members are also included in **35-40 distribution lists and groups**.
7. **Email Confirmation and Onboarding Information:**
    - Once registered, members receive an **email** containing:
        - **Links to all platforms** they have access to.
        - **Usernames and passwords**, along with instructions on how to update their credentials.
        - **Key onboarding sessions** they must attend.
        - A guide on how to navigate and make the most of their membership.
8. **Compliance Quiz Enrollment:**
    - Members are automatically **enrolled in the Compliance Quiz**, which is designed to help them understand the community's **culture, values, and expectations**.
    - The email provides guidance on **how to prepare for the quiz**.
    - Members must **pass the Compliance Quiz within the Induction and Onboarding period**, which lasts **one month from the start of their subscription**.
9. **Database Management:**
    - The database is designed with a **comprehensive structure of tables**, ensuring historical tracking of changes.
    - Each table includes **history tables** that log all modifications, preserving **pre- and post-change values**.
    - For example, if a member updates their phone number, the previous number is recorded in the **member history table**, while the new number is updated in the main **members table**.
    - This approach ensures **auditability and data integrity** across all member-related records.

### 4. Database Overview

The **database** is designed with a **comprehensive structure** of tables to ensure efficiency, scalability, and historical tracking of changes. The architecture includes:

- **Structured Tables:** A well-organized schema that optimizes queries and data integrity.
- **Historical Logging:** Every major table has **history tables** to log all modifications, preserving **pre- and post-change values**.
- **Change Tracking:**
    - Example: If a member updates their phone number, the previous number is recorded in the **member history table**, while the new number is updated in the main **members table**.
    - This ensures **auditability and data integrity** across all records.
- **Stored Procedures:** All database inputs rely on **stored procedures** to ensure consistency, validation, and controlled data modifications.
- **Views for Continuous Access:** Frequently needed data is always available through **predefined views**, ensuring efficient and optimized queries for real-time data access.
- **Version Control and Database Configuration Management:**
    - The current **database schema and data** are extracted as **SQL scripts** and pushed to **version control** to maintain consistency and track changes.
    - There are future plans to **implement database configuration management tools like Liquibase** to automate database deployments and ensure controlled updates.

### 5. Toolkits and Components

The concept behind the toolkits and components is that all interactions with different platforms or the database will be managed through **command-line tools**. Each platform will have a CLI tool tailored for specific operations, and an additional tool will handle **orchestration** across these tools.

Key principles of this approach include:

- **Command-Line Focused Interaction:** Every operation related to the system is executed through CLI tools for automation and scalability.
- **Separation of Concerns:** Each CLI tool is responsible only for processing the **interface**, while all **business logic** is encapsulated within the **components (libraries)**.
- **Maximized Reusability:** The core logic resides within reusable libraries to ensure **efficient reusability** across different toolkits and environments.

To enhance operational efficiency, multiple **toolkits and components** are deployed:

### 5.1 WordPress Automation Toolkit

- **Add and remove members**.
- **Check course registrations and completion status**.
- **Track exam results** (pass/fail status).
- **Disable members when necessary**.
- **Enroll or remove members from specific courses**.
- Automated compliance quiz enrollments.
- Currently uses **Selenium** for UI automation, with plans to transition to **Playwright** in the near future.
- **User management**, including creation, role assignments, and course enrollments.
- Etc.

### 5.2 Question-to-Answer Automation Toolkit

- **Automate member registration and role assignments**.
- **Track member participation and engagement**.
- Automated **member registration and management**.
- Currently uses Selenium for UI automation, with plans to transition to Playwright in the near future.
- Etc.

### 5.3 M365 Toolkit for Microsoft Teams

- **Add members to channels based on their subscription type**.
- **Assign tags to members for better management**.
- **Add members to distribution lists and groups**.
- **Automate message sending for onboarding, reminders, and deadlines**.
- **Send scheduled notifications for exam deadlines and subscription renewals, etc**.
- Member **onboarding/offboarding**.
- Sending **templated messages** (e.g., onboarding welcome, reminders, announcements).
- **Add members to Tags** for Teams channels.
- **Etc.**

### 5.4 Azure Automation Toolkit

- **Disable guest accounts on Azure Cloud**.
- **Enable or disable user accounts as needed**.
- **Upload user profile pictures to their accounts**.
- **Fully automate the onboarding process with complete user data registration**.
- **Automated guest user onboarding** to Azure.
- **Etc.**

### 5.5 Orchestrator CLI

The **Orchestrator CLI** is designed to provide a centralized way to interact with all toolkits and platforms within the system. Instead of executing commands separately for each toolkit, the Orchestrator allows executing **aggregated operations** across multiple platforms efficiently.

Key functionalities include:

- **Automated Multi-Platform Execution:** The Orchestrator interacts with all toolkits in a **silent mode**, ensuring a seamless and automated execution.
- **Batch Processing:** It enables running commands that apply changes across **all platforms** simultaneously. For example, when adding a new member, the Orchestrator CLI will handle registration across **Azure, WordPress, Microsoft Teams, and the Question-to-Answer platform**.
- **Independent Toolkit Execution:** While the Orchestrator provides a unified interface, users can still execute commands for individual toolkits when needed.
- **Efficient Workflow Automation:** Automates repeated tasks like **member onboarding, disabling accounts, or assigning roles across platforms**.

By using the Orchestrator CLI, system administrators can ensure that changes are executed in a structured and efficient manner without manual intervention across different systems.

- Centralized execution for Azure, WordPress, and Question-to-Answer commands.
- Ensures silent and efficient background execution of automation tasks.

### 6. Components and Libraries

To ensure modularity, reusability, and encapsulation of business logic, the system is designed with well-structured libraries and components. These ensure that there is no duplicated code or logic, and all reusable functionalities are parameterized and encapsulated effectively. The key libraries include:

### 6.1 Data Source Interactor

- Responsible for interacting with any data source, including databases.
- Facilitates **data insertion and retrieval** operations.
- Provides an abstraction layer for working with different storage backends.

### 6.2 Markdown Handler

- Manages the **structuring and extraction** of markdown-based data.
- Converts raw data into **structured markdown files** based on predefined templates.
- Supports reading structured markdown files and extracting relevant data for processing.

### 6.3 File System Interactor

- Handles **file system operations**, including reading and writing files.
- Works with other components, such as:
    - CLI tools that generate markdown profiles for members.
    - Writing structured markdown outputs to disk.
    - Reading member details from Excel files for bulk registration processing.

### 6.4 Common Components Library

- Stores all **reusable business logic** shared across multiple toolkits.
- Contains generic functions that cannot be categorized under a specific library but are widely used.

With these components, the system ensures **efficiency, maintainability, and high levels of reusability**, reducing redundant code and improving the development process.

### 7. API Integration

The current system architecture is designed with **command-line interfaces (CLI) interacting directly with libraries**. However, the long-term goal is to introduce a **RESTful API** layer that will consume the business logic from these libraries, making the system more scalable and modular.

#### Key API Considerations:

- **Separation of Concerns:** Instead of having CLI tools interact directly with libraries, the API will act as an intermediary.
- **Standardized Access:** The API will expose a structured and well-documented interface, ensuring a uniform way to interact with the system.
- **Future CLI Evolution:** Once the API is in place, CLI tools will transition to consuming the API rather than libraries, providing a more flexible and scalable approach.
- **Ensuring a Fully API-Ready System:** To guarantee **API readiness**, all **CLI tools** must strictly separate concerns and avoid embedding any business logic directly. Instead, they should only handle **interface processing**, delegating all business logic to reusable libraries or APIs. This ensures that when the transition happens, the system will be fully prepared to switch from CLI-library interactions to an API-driven model without major refactoring.
- **Cost Considerations:** Currently, API implementation has been deferred to minimize hosting costs until the core system is fully developed.

This approach ensures that the system remains **adaptable and future-proof**, allowing smooth migration to an API-based architecture when needed.

### 8. Design Principles

The design of the Elmentor Program is based on the following key principles to ensure a scalable, maintainable, and efficient system:

#### 8.1 Separation of Concerns

- Each component, library, and CLI tool must maintain a **strict separation of concerns**.
- The **business logic is encapsulated within libraries**, while CLI tools serve solely as interfaces.
- This ensures that switching from **direct library interactions to API-based execution** can be done seamlessly in the future.
- Examples of this approach:
    - CLI tools interact with **business logic libraries**, never embedding logic themselves.
    - UI automation (currently using **Selenium**) is modular so that it can be **replaced with Playwright** in the future.
    - Playwright itself can later be replaced with **API interactions** when the platforms support it.

#### 8.2 High Reusability and Modularity

- The entire architecture is designed for **maximum reusability**, reducing redundant logic and improving maintainability.
- All reusable logic is **encapsulated into dedicated libraries**.
- **No business logic should be repeated**—it must always be structured and parameterized within a well-defined library.
- The **Common Components Library** centralizes **shared functionalities**, ensuring no duplication.

#### 8.3 Scalability and Adaptability

- Components are designed to be **independent and loosely coupled**, allowing easy modifications and updates without breaking the system.
- New features can be **added with minimal impact** on existing functionality.
- APIs and CLI tools can be extended or **swapped out without requiring extensive rework**.
- The design enables easy **future integration with external services** or **third-party tools**.

#### 8.4 Technology-Agnostic Approach

- The system avoids **hard dependencies on specific technologies**.
- If a tool or framework (e.g., Selenium) is **replaced with another (e.g., Playwright or API-based automation)**, the transition should be **smooth and non-disruptive**.
- By maintaining **well-defined interfaces**, different implementations can be swapped in and out as needed.

#### 8.5 Maintainability and Code Quality

- Strict adherence to **coding standards and best practices** ensures that the system remains maintainable and extensible.
- The use of **automated testing** and **CI/CD pipelines** guarantees a **stable and reliable system**.
- Documentation is managed using the **Docs as Code approach**, ensuring that developers always have up-to-date references.

By following these principles, the **Elmentor Program** maintains **a flexible, scalable, and highly maintainable system**, ready to adapt to future needs and technological advancements.

- **High Reusability & Modularity:** Each component is designed to be **reused** and **extended**.
- **Abstraction:** Components avoid tight dependencies, allowing future **technology swaps** (e.g., replacing Playwright with API-based automation).
- **Scalability:** Components are structured for **future API exposure**.

### 9. Testing Strategy

A robust **integration and end-to-end testing framework** is implemented to ensure system stability and correctness. Each function within the system must have associated tests to verify that it operates as expected, ensuring all processes complete successfully and meet predefined criteria.

#### 9.1 End-to-End Testing

- Every functional operation must be verified **end-to-end** to confirm that it executes successfully across all platforms.
- Example: If 10 members are registered in WordPress, the test must validate that all **10 users have been successfully registered** by checking the actual user list and ensuring proper role assignments.
- This type of testing ensures that all dependent systems (such as database updates, platform synchronization, and user notifications) work together correctly.

#### 9.2 Integration Testing

- Ensures smooth interaction between different components such as the **CLI tools, business logic libraries, and databases**.
- Example: A test that verifies the **registration process** should check:
    - Data is correctly **retrieved from the input source** (e.g., Excel file).
    - The user is **successfully created in WordPress, Microsoft Teams, and the database**.
    - An email confirmation is **sent with login credentials**.
    - The user is **assigned the correct permissions**.
- Each integration point is **validated to prevent issues from breaking the workflow**.

#### 9.3 Pre and Post-Condition Validation

- Every automated test must **compare the system's state before and after execution**.
- Example: Before registering a new user, the test will confirm they **do not already exist** in WordPress. After the process completes, the test will verify that the user **now appears in the WordPress user list** with the correct attributes.

#### 9.4 Automated Reporting and Debugging

- Every test execution generates a **detailed report**, logging **all actions taken** and confirming whether they were successful.
- Failures must include **error messages and logs** to allow quick debugging.
- Reports are stored and available for **audit tracking**.

By enforcing **end-to-end, integration, and validation testing**, the Elmentor Program ensures that all functionalities are **continuously verified** and the system remains **stable and reliable** at all times.

A robust **integration and end-to-end testing framework** ensures system stability:

- **Verification of all transactions** (e.g., user registration, data consistency, automation execution).
- **Pre and post-condition comparisons** to validate state changes.
- **Reporting and tracking** for debugging and auditability.

### 10. Sync and Data Drift Monitoring

As the **database serves as the Single Source of Truth (SSOT)**, ensuring data consistency across different platforms is critical. The system must continuously monitor, report, and audit data synchronization issues and drift to ensure that every platform reflects the correct state as recorded in the database.

#### 10.1 Data Sync and Integrity Checks

- **Regular Sync Audits:** The system runs scheduled audits to verify that data across **WordPress, Microsoft Teams, Question-to-Answer, and Azure** matches the database.
- **Validation Reports:** The system generates reports showing discrepancies, such as:
    - Members **registered in the database** for a specific course but **missing from the corresponding Microsoft Teams channel**.
    - Users assigned to a course but not appearing in the **WordPress LMS**.
    - Members who passed the **Compliance Quiz** but still have restricted access.
    - Guest accounts that should be disabled but remain active in **Azure**.
- **Sync Automation:** When a discrepancy is detected, the system can automatically trigger corrections or notify the operations team for manual intervention.

#### 10.2 Data Drift Measurement and Reporting

- **Drift Detection Metrics:**
    - Number of users **inconsistently registered across platforms**.
    - Users with **incorrect permissions or missing roles**.
    - Delayed updates where changes in the database are **not yet reflected in platforms**.
- **Comprehensive Reports:**
    - **Daily, weekly, and monthly sync reports** are generated for review.
    - Reports highlight **system-wide drift** and provide **recommended corrective actions**.
- **Operational Alerts:**
    - The system sends **real-time alerts** when data inconsistencies exceed a predefined threshold.
    - Alerts help the operations team take immediate corrective actions.

#### 10.3 Audit Logs and Tracking

- **Historical Tracking:**
    - Every sync operation is logged to track changes over time.
    - The history of discrepancies and corrections is stored for compliance and troubleshooting.
- **Audit Tools:**
    - Administrators can run manual audits on demand to verify system consistency.
    - The system provides detailed logs for troubleshooting sync failures.

By integrating **sync audits, drift monitoring, and automated correction mechanisms**, the system ensures that all **platforms remain aligned with the database**, preventing inconsistencies that could impact the member experience.

### 11. Automation and CI/CD

The automation and continuous integration/continuous deployment (CI/CD) processes are critical to ensuring that all environments are provisioned efficiently, consistently, and securely. The system follows **Terraform best practices** for infrastructure provisioning and ensures **fully automated deployments**.

#### 11.1 Fully Automated Provisioning

- All environments (**development, testing, pre-production, and production**) must be **fully automated** using **Infrastructure as Code (IaC)** principles.
- **Terraform** is the primary tool for managing and provisioning infrastructure, ensuring that deployments are consistent and repeatable.
- **Configuration Management:**
    - The entire infrastructure is stored in **version control** to track changes and maintain consistency.
    - Environments are provisioned based on **predefined Terraform modules** to ensure standardization across all deployments.

#### 11.2 Pre-Production Data Masking and Privacy Compliance

- The **pre-production environment** must include real-world-like data, but with **data masking techniques** applied to protect sensitive information.
- Data masking ensures that personally identifiable information (PII) or confidential data is not exposed in lower environments while still allowing realistic testing scenarios.
- The **data masking process must be fully automated**, ensuring that every refresh of the pre-production database applies masking without manual intervention.

#### 11.3 CI/CD Pipelines and Deployment Automation

- The system follows a **fully automated CI/CD process** to ensure:
    - **Automated builds, testing, and deployments** for all components.
    - **Version-controlled releases** for infrastructure, toolkits, and APIs.
    - **Validation checks** before deployment to prevent configuration drifts.
- **GitHub Actions and Azure DevOps Pipelines** are used to automate the CI/CD workflows.
- The CI/CD pipelines include:
    - **Linting and syntax validation** for infrastructure code.
    - **Automated security scanning** to detect vulnerabilities.
    - **End-to-end and integration testing** before deployment approval.

#### 11.4 Infrastructure and Environment Sync

- To prevent **configuration drift**, the system regularly checks for differences between the **desired state (Terraform configuration) and the actual deployed state**.
- Any drift detected is automatically reported, and corrective actions are triggered to **restore consistency**.
- **Scheduled reconciliation processes** ensure that all infrastructure stays aligned with its intended configuration.

#### 11.5 Observability, Monitoring, and Error Handling

- Every infrastructure and deployment process must be monitored to detect failures early.
- The system uses **logging, monitoring, and alerting** mechanisms to:
    - Track failed deployments.
    - Identify issues in infrastructure provisioning.
    - Trigger **automated rollback mechanisms** if failures occur during deployment.

By following **Terraform best practices, enforcing automated provisioning, implementing data masking in pre-production, and leveraging CI/CD pipelines**, the system ensures that **all deployments are efficient, secure, and scalable**.

### 12. Help and Documentation

Comprehensive documentation is a critical part of the system. Every **public method, CLI command, and future API endpoint** must be well-documented to ensure clarity, usability, and ease of maintenance.

#### 12.1 CLI and API Documentation

- **All CLI commands must be documented** with detailed descriptions, parameters, usage examples, and expected results.
- **Future API endpoints** must also follow the same documentation standard to provide consistency across interfaces.
- **Every command-line tool must have an accessible --help command** that displays structured documentation directly in the terminal.
- **Docs as Code Approach:** The documentation must be structured as part of the codebase and published using platforms like:
    - **GitHub Docs**
    - **Azure DevOps Docs**
    - **A dedicated documentation website**

#### 12.2 Auto-Generated Documentation

- All **CLI methods, public functions, and APIs must include inline XML or Markdown documentation**.
- The documentation must be automatically generated and updated using tools like **Swagger for APIs** and **Doxygen or DocFX for CLI and libraries**.
- This ensures that any change in functionality is reflected immediately in the documentation without manual updates.

#### 12.3 Accessibility and Distribution

- The documentation must be easily accessible to:
    - **Developers via code comments and generated API docs**.
    - **End-users via the --help command in CLI tools**.
    - **Operations teams through a structured documentation portal**.
- **Versioned Documentation:** The system should support multiple documentation versions to allow users to access information relevant to their current software version.

By enforcing a **comprehensive documentation approach**, the Elmentor Program ensures that all functionalities are well-documented, easy to use, and adaptable to future developments.

### 13. Best Practices

To ensure consistency, maintainability, and adherence to industry standards, the Elmentor Program follows common conventions and best practices outlined in our official documentation. These guidelines are based on **established standards and conventions** maintained at:

➡ [**Common Conventions and Standards**](https://github.com/DevOpsVisions/common-workspace-hub/blob/main/docs/standards-and-practices/standards-and-conventions.md)

#### 13.1 Coding and Development Standards

- Standardized **naming conventions** across repositories and codebases.
- Consistent use of **kebab-case, PascalCase, and camelCase** based on context.
- Follow established design patterns to ensure **readability and maintainability**.

#### 13.2 Repository and Workflow Best Practices

- Use **structured GitHub issues and stories** to track development progress.
- Enforce **version control strategies** to maintain a clean and manageable codebase.
- Ensure every repository has **structured release notes** documenting changes.

#### 13.3 Documentation and Compliance

- Follow a **Docs as Code approach** to keep documentation updated alongside the code.
- Ensure every CLI tool and API endpoint is **fully documented** and available in the documentation portal.
- Automate **documentation generation** using tools like **Swagger, DocFX, or Doxygen**.

By following these **best practices and adhering to standardized guidelines**, the Elmentor Program maintains **high-quality, scalable, and well-documented** implementations across all toolkits and components.

### 14. Conclusion

The **Elmentor Program** ensures efficiency, flexibility, and a **seamless user experience**.