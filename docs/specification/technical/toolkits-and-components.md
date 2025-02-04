# Toolkits and Components

The toolkits and components provide a structured way to interact with different platforms and the database using command-line tools. Each platform has a dedicated CLI tool for specific operations, and an additional tool, the **Orchestrator CLI**, enables centralized execution across these tools.

### Key Principles

- **Command-Line Focused Interaction** - Every operation is executed through CLI tools to enhance automation and scalability.
- **Separation of Concerns** - Each CLI tool is responsible only for processing the interface, while all business logic resides within reusable components (libraries).
- **Maximized Reusability** - The core logic is developed as reusable libraries to ensure efficiency across different toolkits and environments.

This architecture ensures flexibility, maintainability, and scalability by keeping logic independent from the execution layer.

## Key Elements of Toolkits

To enhance operational efficiency, multiple toolkits are deployed to automate key platform interactions:

- **Database Automation Toolkit** - Automates database interactions, including data consistency checks, historical tracking, and structured updates.
- **Azure Automation Toolkit** - Manages user access within Azure, handling guest user onboarding, profile updates, and account lifecycle management.
- **M365 Automation Toolkit** - Streamlines Microsoft 365 operations, including Microsoft Teams membership management, role assignments, and automated messaging.
- **WordPress Automation Toolkit** - Automates user registration, course enrollments, and compliance tracking within the WordPress-based learning platform.
- **Question-to-Answer Automation Toolkit** - Handles automated member registration, role assignments, and engagement tracking within the Q&A platform.
- **Orchestrator CLI** - A centralized tool that executes multi-platform commands, enabling streamlined workflow automation across all toolkits.

The following sections provide a detailed breakdown of each toolkit and its functionalities.

## Database Automation Toolkit

The Database Automation Toolkit focuses on automating database interactions, primarily for inserting, querying, and managing data efficiently. It is designed to handle structured data operations while maintaining consistency and integrity. Additionally, it supports database backups and the extraction of schemas and data as SQL scripts.

### Features:

- Automate the insertion and validation of new records.
- Ensure compliance with structured data changes and historical logging.
- Maintain consistency by enforcing predefined validation rules.
- Automate database backups.
- Extract schema and data as SQL scripts for versioning and reference.
- Support efficient querying of stored data for reporting and analysis.
- No integration with Liquibase; primarily focused on direct database interactions and management.

## Azure Automation Toolkit

The Azure Automation Toolkit manages user access within Azure, ensuring smooth onboarding and account lifecycle management.

### Features:

- Disable guest accounts on Azure Cloud when required.
- Enable or disable user accounts as needed.
- Upload user profile pictures to their accounts.
- Fully automate the onboarding process with complete user data registration.
- Automate guest user onboarding and lifecycle management.

## M365 Automation Toolkit

The M365 Automation Toolkit streamlines Microsoft 365 operations by automating member access, messaging, and group management.

### Features:

- Add members to Teams channels based on their subscription type.
- Assign tags to members for better organization and permissions control.
- Add members to distribution lists and groups.
- Automate message sending for onboarding, reminders, and deadlines.
- Send scheduled notifications for exam deadlines, subscription renewals, and general announcements.
- Manage member onboarding and offboarding.
- Automate sending templated messages such as onboarding welcomes and reminders.

## WordPress Automation Toolkit

The WordPress Automation Toolkit manages user registration, course enrollments, and compliance tracking. It automates operations related to membership management and course progress tracking.

### Features:

- Add and remove members.
- Check course registrations and track completion status.
- Track exam results, including pass/fail status.
- Disable members when necessary.
- Enroll or remove members from specific courses.
- Automate compliance quiz enrollments.
- Manage user roles, assignments, and course enrollments.
- Currently utilizes Selenium for UI automation, with planned migration to Playwright.

## Question-to-Answer Automation Toolkit

The Question-to-Answer Automation Toolkit automates member registration and engagement tracking. This ensures members are properly assigned roles and can participate effectively in knowledge-sharing activities.

### Features:

- Automate member registration and role assignments.
- Track member participation and engagement.
- Manage automated user registration and updates.
- Currently utilizes Selenium for UI automation, with planned migration to Playwright.

## Orchestrator CLI

The Orchestrator CLI provides a centralized mechanism for executing commands across all toolkits and platforms. Instead of manually executing separate commands for each toolkit, the Orchestrator CLI enables efficient execution of aggregated operations.

### Features:

- **Automated Multi-Platform Execution** - Executes commands in silent mode, interacting with all toolkits seamlessly.
- **Batch Processing** - Enables running commands that apply changes across all platforms simultaneously. For example, adding a new member triggers automated registration across Azure, WordPress, Microsoft Teams, and the Question-to-Answer platform.
- **Independent Toolkit Execution** - Users can execute commands for individual toolkits when needed.
- **Efficient Workflow Automation** - Automates repeated tasks such as member onboarding, disabling accounts, and role assignments across platforms.
- **Centralized Execution** - Provides a single command-line interface to control Azure, WordPress, and Question-to-Answer processes.
- **Ensures Silent and Efficient Background Execution** - Minimizes manual intervention while maintaining structured execution.

This unified approach ensures that system administrators can efficiently manage platform interactions, reducing manual overhead while improving consistency and reliability.
