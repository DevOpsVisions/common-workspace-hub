# Common Conventions and Standards
This document provides guidance on common conventions and standards, including examples but without specific values. For precise conventions and values, please refer to the detailed guidelines within each individual project and repository.

## Repository and Application

This section outlines the objects that should standardized naming conventions used throughout all projects to maintain consistency and clarity:

- **Repository Name**: The full, descriptive name for the project repository, reflecting its purpose.
- **Application Name**: The concise, user-friendly name for the application, ideal for branding and communication.
- **Executable Name**: The short and efficient name used for the executable file, optimized for easy reference in scripts and command-line usage.

## Solution and Projects

To maintain a structured and organized codebase, the following naming conventions are used for the solution and project files:

- **Solution File**: The overarching solution file that includes all related projects.
- **Project Files**:
  - One main project file for the core application.
  - One project file dedicated to unit tests.
  - One project file dedicated to integration tests.

## Azure Cloud

A well-structured naming convention for Azure resources is crucial for quickly identifying the resource type, associated workload, environment, Azure region, and instance. Our naming convention follows these key elements:

### Example:

- **Resource Type:** `vm`, `st`, `appsvc`, `sql`, `nsg`, `kv`, `rg`, `pip`, `aks`, `lb`
- **Workload/Application:** `webapp`, `api`, `hrportal`, `crm`, `salesdata`, `logs`
- **Environment:** `prod`, `dev`, `test`, `staging`, `qa`, `uat`
- **Azure Region:** `eastus`, `westeurope`, `centralus`, `westus2`, `southeastasia`, `uksouth`
- **Instance:** `001`, `002`, `003`, `004`, `005`


More info: [Microsoft Azure Docs](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming)

## **GitHub Organization and Project Naming Conventions**  

To ensure consistency and clarity across all Organization and Projects, we adopt the following naming conventions:  

### **GitHub Organization Name**  
- **URL Format**: `https://github.com/DevOpsVisions` (PascalCase)  
- **Display Name**: `DevOps Visions` (Pascal with spaces)  

### **GitHub Project Name**  
The GitHub Project Name should be the same as the repository name but formatted in **Pascal Case with spaces** for readability and branding.

- **Example**: `Azure Automation Toolkit`  
- The corresponding repository URL would be: `https://github.com/DevOpsVisions/azure-automation-toolkit`

## Repository Folder Structure

The following is the folder structure used within the repository to maintain a clear and organized layout:

### Folder Structure and Descriptions for App Repos

- **/docs**: Contains all documentation related to the project.
  - **/standards-and-practices**: Holds documents outlining the standards and practices followed in the project.
  - **/technical-guides**: Contains guides for deploying and managing the project, like `deploy-q2a-azure-vm.md`.

- **/src**: The source code directory.
  - **/app**: Holds the application code.
  - **/iac**: Infrastructure as Code (IaC) files and configurations.
    - **/scripts**: Shell scripts for automation.
      - **setup.sh**: Script to set up the environment.
      - **destroy.sh**: Script to tear down the environment.
      - **backup.sh**: Script to create backups.
    
    - **/terraform**: Shared Terraform configuration files.
      - **main.tf**: Shared resources configuration across all environments.
      - **variables.tf**: Shared variable definitions.
      - **outputs.tf**: Shared outputs.
      - **provider.tf**: Provider configuration.
      - **versions.tf**: Terraform version constraints.
      - **/env-override**: Environment-specific variable overrides.
        - **dev.tfvars**: Overrides for the development environment.
        - **staging.tfvars**: Overrides for the staging environment.
        - **prod.tfvars**: Overrides for the production environment.

      - **/modules**: Reusable Terraform modules.
        - **/network**: Networking-related Terraform module.
          - **main.tf**: Main configuration for the network module.
          - **variables.tf**: Variable definitions for the network module.
          - **outputs.tf**: Output values for the network module.
        - **/compute**: Compute-related Terraform module.
          - **main.tf**: Main configuration for the compute module.
          - **variables.tf**: Variable definitions for the compute module.
          - **outputs.tf**: Output values for the compute module.
        - **/storage**: Storage-related Terraform module.
          - **main.tf**: Main configuration for the storage module.
          - **variables.tf**: Variable definitions for the storage module.
          - **outputs.tf**: Output values for the storage module.

      - **/environments**: Environment-specific configurations.
        - **/dev**: Development environment configurations.
          - **main.tf**: Main configuration for the development environment.
          - **terraform.tfvars**: Variable values specific to the development environment.
        - **/staging**: Staging environment configurations.
          - **main.tf**: Main configuration for the staging environment.
          - **terraform.tfvars**: Variable values specific to the staging environment.
        - **/prod**: Production environment configurations.
          - **main.tf**: Main configuration for the production environment.
          - **terraform.tfvars**: Variable values specific to the production environment.

### Folder Structure and Descriptions for DB Repos

- **/docs**: Contains all documentation related to the project.
  - **/standards-and-practices**: Holds documents outlining the standards and practices followed in the project.
  - **/technical-guides**: Contains guides for deploying and managing the project, including database-related guides.

- **/src**: The source code directory.
  - **/db**: Contains all database-related files.
    - **/schemas**: Holds database schema definition files, such as table structures, relationships, and indexes.
    - **/stored-procedures**: Contains stored procedure scripts that encapsulate business logic.
    - **/functions**: Contains scripts for database functions, including scalar and table-valued functions.
    - **/views**: Holds SQL scripts that define database views.
    - **/triggers**: Contains scripts for database triggers, such as after/insert/update/delete triggers.
    - **/migrations**: Contains migration scripts for handling schema changes, versioning, and updates to the database.
    - **/scripts**: Contains additional SQL scripts or utility scripts that do not fit into other specific categories.
    - **/seed-data**: Holds data seeding scripts for populating the database with initial or test data.
    - **/backups**: Contains database backup files. (Ensure sensitive information is handled appropriately.)
    - **/configs**: Holds configuration files related to database connections, environment settings, or other relevant configurations.
    - **/indexes**: Contains SQL scripts for defining indexes used in the database.
    - **/constraints**: Holds scripts for defining constraints, such as primary keys, foreign keys, and unique constraints.

  - **/iac**: Infrastructure as Code (IaC) files for setting up the environment, including database provisioning and configuration scripts.

### Folder Structure and Descriptions for GitHub Actions

- **/.github**: Contains GitHub Actions workflows and configurations.
  - **/workflows**: Default directory for GitHub Action workflows.
    - **main.yml**: Main workflow for CI/CD pipeline.
    - **test.yml**: Testing workflow.
    - **deploy.yml**: Deployment workflow.
    - **dispatch.yml**: Manual or scheduled workflow trigger.
    - **/reusable-workflows**: Contains reusable workflows.
      - **linting.yml**: Linting reusable workflow.
      - **test-reusable.yml**: Testing reusable workflow.
      
  - **/actions**: Custom GitHub Actions defined in the repository.
    - **/my-custom-action**: Custom action directory.
      - **Dockerfile**: Dockerfile for the custom action.
      - **action.yml**: Metadata file for the custom action.
      - **entrypoint.sh**: Entrypoint script for the custom action.
      
  - **/scripts**: Utility scripts used in workflows.
    - **deploy.sh**: Script for deployment.
    - **test.sh**: Script for running tests.
    - **lint.sh**: Script for linting.

### Benefits of This Structure

#### App Repositories

1. **Separation of Concerns**: The structure separates documentation, application code, and infrastructure configurations, making it easier to manage and navigate.
2. **Scalability**: The modular approach in `iac/terraform/modules` and environment-specific configurations under `environments/` allow the project to scale without cluttering the repository.
3. **Maintainability**: Clear organization of application logic, infrastructure, and scripts simplifies maintenance and updates, as changes can be localized to specific directories.

#### Infrastructure as Code (IaC)

1. **Modularization**: Reusable Terraform modules allow for a consistent setup across different environments and projects, reducing duplication and the potential for errors.
2. **Environment-Specific Configurations**: The `env-override` and `environments` directories enable tailored infrastructure configurations for dev, staging, and production environments, promoting best practices for managing different deployment stages.
3. **Automation**: Scripts in the `scripts` directory automate repetitive tasks, enhancing efficiency and reducing the risk of human error during infrastructure management.

#### Database Repositories

1. **Clear Organization**: The separation of different database components (schemas, stored procedures, functions, etc.) into their own directories makes it easy to locate and manage specific parts of the database.
2. **Version Control and Migrations**: The `migrations` directory supports version control of the database schema, making it easier to track and apply changes over time.
3. **Consistency and Best Practices**: By organizing the database code and configurations according to established standards and practices, the structure helps ensure the integrity and quality of the database.


#### GitHub Actions

1. **Organization**: Clearly separates different types of workflows and actions, making the repository easy to navigate and understand.
2. **Reusability**: Reusable workflows allow common tasks to be shared across multiple workflows or repositories, reducing duplication and ensuring consistency.
3. **Maintainability**: Specific parts of the workflow, such as deployment or testing scripts, can be updated independently without affecting other workflows.
4. **Scalability**: New workflows, scripts, or actions can be added without cluttering the main workflows directory, allowing for easy expansion as the project grows.

Overall, this structure promotes clarity, reusability, and maintainability across the app, infrastructure, and database repositories.

## Release Notes Template 
The following is the release note template used to organize key details of a product update, including release date, developer info, version, new features, bug fixes, and downloadable assets. It ensures clear communication of changes to users.

|<p>**Date**</p><p>**@Develper account**</p><p> **Tag**</p><p> **Commit** <br />&nbsp;<br /> <br />&nbsp;<br /><br />&nbsp;<br /><br />&nbsp;<br /><br />&nbsp;<br /><br />&nbsp;<br />  </p>|<p>**Product Name version** </p><p> (Org name/link) released from (n) days ago &nbsp; &nbsp; (tag) &nbsp; &nbsp; &nbsp; &nbsp; (commit) </p><p></p><p> Version (Release Date)</p><p></p><p>**Features Added:**</p><p>- Issue Title (Issue ID, PR ID) </p><p></p><p>**Bugs Fixed:**</p><p>- Issue Title (Issue ID, PR ID) </p><p></p><p>**Assets**</p><p> App (zip)	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Date </p><p> Source code (zip) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Date</p><p></p>|
| :- | :- |

## Kebab Case
By adopting the kebab case for URLs, file names, Azure resources, and GitHub repositories, the projects maintain clarity and uniformity across different web assets, cloud infrastructure, and code repositories, improving both collaboration and readability.
- **Purpose**: Kebab case is used to enhance readability and maintain uniformity in naming conventions. This format, which uses lowercase letters and hyphens to separate words (e.g., `project-name`, `user-profile`), is applied consistently across multiple contexts.

- **Use Cases Relevant to Our Projects**:
  - **URLs and Slugs**: Clean, SEO-friendly URLs (e.g., `https://example.com/user-profile/settings`).
  - **File Names**: Consistently formatted file names across different environments, ensuring clarity and ease of management (`data-fetching-service.js`).
  - **Folder Names**: All folder names (e.g., `project-assets`, `user-profiles`), providing a consistent approach to organizing directories in both local and cloud environments.
  - **Azure Resources**: All Azure resource names (such as storage accounts, databases, and resource groups) will follow the kebab case convention (e.g., `my-storage-account`), aligning with Azure's naming guidelines for easier resource identification and management.
  - **GitHub Repositories**: Repository names on GitHub will use kebab case (e.g., `project-management-tool`), providing consistency across version control and collaboration efforts.

By using kebab case, these examples demonstrate a clear and consistent naming convention that is both readable and suitable for various web and programming contexts.


For more information on kebab case, you can refer to this detailed [guide on MDN Web Docs](https://developer.mozilla.org/en-US/docs/Glossary/Kebab_case) or this article on [SmartWP](https://smartwp.com/kebab-case/).

## PascalCase
PascalCase is used for naming conventions where each word starts with an uppercase letter. This style is commonly used for naming classes, methods, public properties, and interfaces in C#.

- **Purpose**: Enhances readability and provides a consistent format for naming elements that are publicly accessible or part of the overall architecture.

- **Use Cases Relevant to Our Projects**:
  - **Class Names**: All class names will use PascalCase (e.g., `UserService`, `DataProcessor`), ensuring clear identification and alignment with C# standards.
  - **Method Names**: Method names will also follow PascalCase (e.g., `FetchData`, `SaveChanges`), making them easily recognizable as functions.
  - **Interfaces**: Interfaces will be named using PascalCase and typically start with an "I" (e.g., `IConfigurationService`), distinguishing them from regular classes.
  - **Public Properties**: Public properties will use PascalCase (e.g., `UserName`, `OrderDate`), providing consistency across publicly accessible fields.

## camelCase
camelCase is used for naming conventions where the first letter is lowercase and each subsequent word starts with an uppercase letter. This style is typically used for local variables, method parameters, and private fields.

- **Purpose**: Maintains clarity and differentiation between local elements and public or architectural components, supporting a clean and organized code structure.

- **Use Cases Relevant to Our Projects**:
  - **Variables and Parameters**: Local variables and method parameters will use camelCase (e.g., `userName`, `orderDetails`), enhancing readability within methods and distinguishing them from other elements.
  - **Private Fields**: Private fields within classes often use camelCase (e.g., `configValue`, `itemCount`), keeping them distinct from public properties and adhering to internal consistency.


## Command Line Interface (CLI) Silent Mode

To enhance usability and maintain a consistent approach across our toolkits and frameworks, all CLI tools will support a silent mode. This mode allows commands to be executed without interactive prompts, facilitating automation and script integration. Below are the guidelines for implementing silent mode:

### Method and Function Naming

- **Naming Convention**: All methods or functions called via CLI should use kebab case notation. This involves using lowercase letters with words separated by hyphens.
- **Examples**:
  - `OurToolKit.exe add-user`
  - `OurToolKit.exe add-users`
  - `OurToolKit.exe remove-user`
  - `OurToolKit.exe list-users`
  - `OurToolKit.exe update-user`
  - `OurToolKit.exe reset-password`

### Parameter Naming

- **Naming Convention**: Parameters should follow the kebab case notation and be prefixed with two hyphens (`--`). For commonly used parameters, abbreviated versions are allowed.
- **Examples**:
  - `--user-name -un`
  - `--password -pass`
  - `--email -e`
  - `--role -r`
  - `--output-file -o`
  - `--start-date -sd`
  - `--end-date -ed`

### Parameter Descriptions

- Each parameter must include a clear description of its purpose. The description should be concise and directly associated with the parameter in the help documentation.
- **Example Descriptions**:
  - `--user-name`: The full name of the user to be added or managed (e.g., `"John Doe"`).
  - `--password`: The user's password for authentication (e.g., `"SecurePass123"`).
  - `--email`: The email address of the user (e.g., `"johndoe@example.com"`).
  - `--role`: The role assigned to the user (e.g., `"admin"`, `"editor"`).
  - `--output-file`: The path to the output file where results will be saved (e.g., `"results.txt"`).
  - `--start-date`: The start date for the report in `YYYY-MM-DD` format (e.g., `"2024-09-12"`).
  - `--end-date`: The end date for the report in `YYYY-MM-DD` format (e.g., `"2024-09-19"`).

### Parameter Values

- **Format**: Parameters are followed directly by their values.
- **Examples**:
  - `--user-name "Mohamed Radwan"`
  - `--password "SecurePass123"`
  - `--email "mohamed.radwan@example.com"`
  - `--role "admin"`
  - `--output-file "C:\results\output.txt"`
  - `--start-date "2024-09-01"`
  - `--end-date "2024-09-30"`

### Help and Usage Information

- **Help Command**: Each method should support a help command (`--help`) that displays all available parameters, their descriptions, and examples of usage.


### Example Output of `--help`

For a command like `OurToolKit.exe add-user --help`, the output should look like this:

### Description

The `add-user` command is used to add a new user to the system. This command allows you to specify various attributes for the user, such as their name, password, email, role, and other optional details like department and active dates.

#### Usage
Usage: OurToolKit.exe add-user [options]

#### Options

- `--user-name, -un`  
  The full name of the user to be added (e.g., "John Doe").

- `--password, -pass`  
  The password for the new user (e.g., "SecurePass123").

- `--email, -e`  
  The email address of the user (e.g., "johndoe@example.com").

- `--role, -r`  
  The role assigned to the user (e.g., "admin", "editor").

- `--department, -d`  
  The department to which the user belongs (e.g., "Sales", "IT").

- `--start-date, -sd`  
  The start date for the user in the format YYYY-MM-DD (e.g., "2024-09-01").

- `--end-date, -ed`  
  The end date for the user in the format YYYY-MM-DD (e.g., "2024-09-30").

- `--help`  
  Show this help message and exit.

#### Examples

**Adding a New Admin User:**

`OurToolKit.exe add-user --user-name "John Doe" --password "SecurePass123" --email "johndoe@example.com" --role "admin"`

By adopting these guidelines, we ensure that our CLI tools are user-friendly, well-documented, and consistent across all toolkits and frameworks, enhancing the overall developer experience.


## GitHub Titles

To distinguish between issues and pull requests (PRs) on GitHub while following best practices, we use specific conventions for titles. This approach ensures consistency, clarity, and organization within our repositories.

- **Purpose**: These conventions are designed to enhance communication and streamline the development process, making it easier to identify and understand each item, thereby improving collaboration and efficiency.

**GitHub Issue Title:**

Format: `[Type] - [Component/Area] - [Brief Description of Problem or Need]`

Example: `Bug - User Authentication - Error When Logging In`

- **[Type]**: Indicate the type of issue, such as Bug, Feature, Story, Improvement, Task, Documentation, or Refactor.
- **[Component/Area]**: Mention the specific component, feature, or area of the project affected (e.g., User Authentication, UI, API).
- **[Brief Description of Problem or Need]**: Provide a short and clear description of the problem, need, or request.

**Pull Request (PR) Title:**

Format: `[Action] - [Component/Area] - [Brief Description of Change] (Issue ID)`

Example: `Refactor - User Authentication - Simplify Login Logic (#456)`

- **[Action]**: Specify the action being taken, such as Add, Fix, Refactor, Update, Remove, Enhance, or Document.
- **[Component/Area]**: Mention the specific component, feature, or area of the project affected (e.g., User Authentication, UI, API).
- **[Brief Description of Change]**: Provide a concise description of the change or improvement.
- **(Issue ID)**: Include the relevant issue ID in parentheses to link the PR to the corresponding issue.

**Examples:**

- **Issue Title**: `Feature - Dashboard - Add User Analytics Section`
- **PR Title**: `Add - Dashboard - User Analytics Section (#123)`

By distinguishing between the purpose of an issue (describing a problem or request) and a pull request (indicating a specific action taken to address an issue), the titles become more informative and aligned with best practices for collaborative development.

### More Examples for Issues:

1. **Bug Reports:**
   - `Bug - API - Null Pointer Exception on Empty Input`
   - `Bug - User Profile - Image Upload Fails on Large Files`
   
2. **Feature:**
   - `Feature - Dashboard - Add User Analytics Section`
   - `Feature - Notifications - Enable Push Notifications`

3. **User Stories:**
   - `Story - Shopping Cart - Save items for later in the shopping cart`
   - `Story - Notifications - Enable email alerts for important updates`


4. **Improvements:**
   - `Improvement - UI - Enhance Accessibility for Screen Readers`
   - `Improvement - Performance - Optimize Database Queries for Reports`

5. **Documentation:**
   - `Documentation - API - Add Examples for Authentication Endpoints`
   - `Documentation - Setup Guide - Update Instructions for Windows Installation`

6. **Questions:**
   - `Question - API - Clarification Needed on Rate Limiting`
   - `Question - UI - Best Practices for Custom Theming`

### More Examples for Pull Requests (PRs):

1. **Bug Fixes:**
   - `Fix - API - Handle Null Pointer Exception on Empty Input (#101)`
   - `Fix - User Profile - Correct Image Upload Logic (#202)`

2. **Feature Additions:**
   - `Add - Dashboard - User Analytics Section (#303)`
   - `Add - Notifications - Implement Push Notifications Feature (#404)`

3. **Improvements:**
   - `Enhance - UI - Improve Accessibility for Screen Readers (#505)`
   - `Optimize - Performance - Refactor Database Queries for Reports (#606)`

4. **Refactoring:**
   - `Refactor - User Authentication - Simplify Login Logic (#707)`
   - `Refactor - Codebase - Modularize CSS for Better Maintainability (#808)`

5. **Documentation Updates:**
   - `Document - API - Add Usage Examples for Authentication Endpoints (#909)`
   - `Update - Setup Guide - Revise Windows Installation Instructions (#1010)`
