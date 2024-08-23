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
