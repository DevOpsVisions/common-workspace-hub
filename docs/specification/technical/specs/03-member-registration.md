# Member Registration Process

The member registration process is a structured workflow designed to ensure seamless onboarding and data integrity. It involves multiple steps, including data collection, processing, database registration, platform integrations, access management, and compliance verification. Each step plays a critical role in securing member information, assigning appropriate roles, and ensuring a smooth transition into the community.

## Key Steps in the Registration Process:

1. **Data Collection** - Members fill out a registration form that includes a Non-Disclosure Agreement (NDA) and data privacy terms.
2. **Data Processing** - The submitted data is validated, ensuring key fields such as qualification, experience, and unique identifiers are handled correctly.
3. **Database Registration** - The member data is recorded and stored in the database with historical tracking for accuracy and auditability. The database serves as the **Single Source of Truth (SSOT)** for all membership information.
4. **Azure Tenant Integration** - Members are added as guest accounts in the Azure Tenant for authentication and access control.
5. **Microsoft Teams Integration** - Members are added to designated channels, assigned tags, and included in distribution lists.
6. **WordPress Registration** - Members receive appropriate roles based on their subscription and gain access to relevant courses.
7. **Question-to-Answer Platform Registration** - Members are added to the platform with permissions corresponding to their roles.
8. **Compliance Quiz Enrollment** - Members must complete a quiz to understand the community’s values and expectations.
9. **Email Confirmation and Onboarding Information** - Members receive account details, login credentials, and onboarding guidance after being registered in all systems, including the compliance quiz.

## Detailed Steps

### Data Collection

The registration process begins with members filling out a Microsoft Form, which gathers essential information required for onboarding. This form includes a **Non-Disclosure Agreement (NDA)**, ensuring members acknowledge and agree to data privacy policies. The information collected includes qualification, years of experience, specialization, and subscription type.

#### Key Data Collected:

- Qualification and years of experience.
- Specialization and area of expertise.
- Type of subscription.
- **Also Known As (AKA) Identifier** – A unique identifier that ensures distinct membership names. If a duplicate is detected, it is slightly modified based on the family name to maintain uniqueness.

### Data Processing

Once the data is collected, it undergoes a validation process to check for completeness and accuracy. We ensure that the data has been recorded correctly and that it matches the subscription type and other details. After validation, the file is downloaded in **Excel format** to be used in subsequent operations.

#### Key Processing Steps:

- Ensure all required fields are filled accurately.
- Validate uniqueness of identifiers to prevent duplicates.
- Verify qualification and experience align with membership criteria.
- Confirm essential details, including personal links and years of experience.
- The Excel file downloaded from Microsoft Forms is amended by adding extra information and values, which is then used as the input for the entire registration process.

### Database Registration

After data validation and processing, the member data is stored securely in the database, ensuring long-term accuracy and historical tracking. The database serves as the **Single Source of Truth (SSOT)** for all member-related information.

#### Data Integrity Measures:

- **History tables** log all modifications for transparency.
- Pre- and post-change values are recorded to maintain accuracy.
- The structure ensures that all member-related records remain auditable.
- **Role Assignment**: As part of the database registration process, member roles are recorded, including **Member**, **Mentor**, **GA (Group Advisory)**, **LGA (Lead Group Advisory)**, **BD (Business Development)**, **LBD (Lead Business Development)**, and other relevant roles as necessary.

### Azure Tenant Integration

After database registration, members are added as guest accounts in the **Azure Tenant**, ensuring authentication and access control.

#### Integration Steps:

- Secure identity management is applied for authentication.
- Role-based access control is assigned based on the membership type.

### Microsoft Teams Integration

Once members are added to Azure, they are integrated into Microsoft Teams. This step enables structured communication and collaboration through role-based channel access and distribution lists.

#### Channel and Group Assignments:

- Members join approximately **90 Teams channels** categorized by topics and activities.
- **Tags are assigned** based on membership and subscription type.
- Members are included in **35-40 distribution lists** for structured communication.

### WordPress Registration

At this stage, members are granted access to the WordPress-based learning platform. This step ensures that members can engage with structured learning content based on their assigned roles.

#### Membership and Course Enrollment:

- Members are assigned specific roles based on their subscription.
- **Learning Management System (LMS) Enrollment** ensures access to relevant courses.
- Access is controlled using the **Membership plugin** for authentication.

### Question-to-Answer Platform Registration

Following WordPress registration, members are onboarded onto the **Question-to-Answer Platform**. This step ensures they can actively participate in structured Q&A discussions, contribute their expertise, and seek guidance from the community.

#### Registration Steps:

- Members are added based on their roles.
- Permissions are configured according to the subscription level.

### Compliance Quiz Enrollment

To ensure alignment with the community’s values and policies, new members must complete a **Compliance Quiz**. This quiz assesses members' understanding of the guidelines, ethical conduct, and expectations within the community.

#### Quiz Details:

- The quiz helps members understand community culture and policies.
- Members receive guidelines on preparation.
- Completion is mandatory within the **first month (Induction and Onboarding period).**

### Email Confirmation and Onboarding Information

Once members have been fully registered in all platforms, including the compliance quiz, they receive an onboarding email with essential details. This email serves as an important guide, providing members with access credentials, an overview of available resources, and guidance on how to navigate their membership effectively.

#### Email Contents:

- Links to all accessible platforms.
- User credentials and instructions for updating them.
- A schedule of **key onboarding sessions**.
- A detailed guide on preparing for and completing the **Compliance Quiz**.
- Best practices for maximizing community engagement.

This structured registration process ensures a smooth onboarding experience, secure data management, and seamless integration into the community.
