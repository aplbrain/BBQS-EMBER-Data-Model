# Access Control Features in EMBER

## Overview
This document outlines the access control features implemented in the EMBER system, focusing on role-based access, project-specific permissions, data handling during embargo periods, and other security measures for Public, Restricted, and PHI/PII data.

### Role-Based Access Control 
- **Roles Defined**: Project owner, contributors, EMBER admin
- **Access Restrictions**: Based on individual roles within an organization to restrict access to resources

### Project-Based Permissions
- **Project Specific Controls**: Each project can have specific access controls
- **Permissions**: Dictate who can see and manipulate data
- **Admin Review**: EMBER admin reviews controls set by the project owner

### Optional Embargo Periods
- **Embargo Settings**: Ability to set an embargo period where data is only available to certain contributors
- **End of Embargo**: Data becomes publicly accessible or available to a broader audience after the embargo period

### Access Levels for Data Types
- **Metadata vs. Full Data Sets**: Differentiating access between just metadata or the full datasets
- **Sensitive Data**: Special considerations for Restricted and PHI/PII data classes

### User Authentication and Authorization
- **Authentication**: Ensures users are who they claim to be
- **Authorization**: Users have appropriate permissions to access specific datasets

### Audit Trails and Logs
- **Monitoring Access**: Keeps track of who accesses data and when
- **Compliance**: Essential for compliance with legal and security standards

### Data Encryption
- **Security Measures**: Encrypts data in transit and at rest
- **Protect Sensitive Information**: Prevents unauthorized access to sensitive data

## Conclusion
These features are integrated into the EMBER Portal to manage different types of data across varying levels of sensitivity, ensuring both compliance with governance standards and protection of sensitive information.
