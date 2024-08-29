# Common Conventions and Standards


## Repository and Application

This section outlines the standardized naming conventions used throughout both projects to maintain consistency and clarity:

- **Repository Name**: The full, descriptive name for the project repository, reflecting its purpose.
- **Application Name**: The concise, user-friendly name for the application, ideal for branding and communication.
- **Executable Name**: The short and efficient name used for the executable file, optimized for easy reference in scripts and command-line usage.

## Solution and Projects

To maintain a structured and organized codebase, the following naming conventions are used for the solution and project files:

- **Solution File**: The overarching solution file that includes all related projects.
- **Project Files**:
  - The main project file for the core application.
  - The project file dedicated to unit tests.
  - The project file dedicated to integration tests.

## Azure Cloud

A well-structured naming convention for Azure resources is crucial for quickly identifying the resource type, associated workload, environment, Azure region, and instance. Our naming convention follows these key elements:

### Example:

- **Resource Type**
- **Workload/Application**
- **Environment**
- **Azure Region**
- **Instance**

More info: [Microsoft Azure Docs](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming)

## Repository Folder Structure

The following is the folder structure used within the repository to maintain a clear and organized layout:

### Folder Descriptions

- **/docs**: Contains all documentation related to the project.
  - **/standards-and-practices**: Holds documents outlining the standards and practices followed in the project.
  - **/technical-guides**: Contains guides for deploying and managing the project, like `deploy_q2a_azure_vm.md`.
  
- **/src**: The source code directory.
  - **/app**: Holds the application code.
  - **/iac**: Infrastructure as Code (IaC) files for setting up the environment.


## Release Notes Template 
The following is the release note template used to organize key details of a product update, including release date, developer info, version, new features, bug fixes, and downloadable assets. It ensures clear communication of changes to users.

|<p>**Date**</p><p>**@Develper account**</p><p> **Tag**</p><p> **Commit** <br />&nbsp;<br /> <br />&nbsp;<br /><br />&nbsp;<br /><br />&nbsp;<br /><br />&nbsp;<br /><br />&nbsp;<br />  </p>|<p>**Product Name version** </p><p> (Org name/link) released from (n) days ago &nbsp; &nbsp; (tag) &nbsp; &nbsp; &nbsp; &nbsp; (commit) </p><p></p><p> Version (Release Date)</p><p></p><p>**Features Added:**</p><p>- Issue Title (Issue ID, PR ID) </p><p></p><p>**Bugs Fixed:**</p><p>- Issue Title (Issue ID, PR ID) </p><p></p><p>**Assets**</p><p> App (zip)	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Date </p><p> Source code (zip) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Date</p><p></p>|
| :- | :- |

## Kebab Case

- **Purpose**: Kebab case is used to enhance readability and maintain uniformity in naming conventions. This format, which uses lowercase letters and hyphens to separate words (e.g., `project-name`, `user-profile`), is applied consistently across multiple contexts.

- **Use Cases**:
  - **URLs and Slugs**: Clean, SEO-friendly URLs (e.g., `https://example.com/user-profile/settings`).
  - **File Names**: Consistently formatted file names across different environments, ensuring clarity and ease of management (`data-fetching-service.js`).
  - **Azure Resources**: All Azure resource names (such as storage accounts, databases, and resource groups) will follow the kebab case convention (e.g., `my-storage-account`), aligning with Azure's naming guidelines for easier resource identification and management.
  - **GitHub Repositories**: Repository names on GitHub will use kebab case (e.g., `project-management-tool`), providing consistency across version control and collaboration efforts.

By adopting the kebab case for URLs, file names, Azure resources, and GitHub repositories, the projects maintain clarity and uniformity across different web assets, cloud infrastructure, and code repositories, improving both collaboration and readability.

For more information on kebab case, you can refer to this detailed [guide on MDN Web Docs](https://developer.mozilla.org/en-US/docs/Glossary/Kebab_case) or this article on [SmartWP](https://smartwp.com/kebab-case/).
