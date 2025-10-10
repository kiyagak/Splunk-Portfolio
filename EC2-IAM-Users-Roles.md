## Objective

The goal is to make a new user within Splunk Enterprise that has
- basic access search and reporting capabilities without advanced or administrative permissions
- is a data manager that manages lifecycle of data management agents like Edge Processors, including onboarding, monitoring, and updates

## Create a New User

Click on **Settings**.  
Under Users and Authentication click **Users**.  

<img width="1141" height="637" alt="image" src="https://github.com/user-attachments/assets/c80a19a9-c71c-4af0-ac98-e00d8bbbe5d8" />

Click **New User**:

<img width="1134" height="361" alt="image" src="https://github.com/user-attachments/assets/1da972cc-2858-4b00-bd82-23868bcbeb96" />

About the roles:
- The Splunk user role grants basic access to run searches, create personal saved searches, and define event types. It provides fundamental search and reporting capabilities without advanced or administrative permissions.
- The data_management_agent Splunk role manages lifecycle of data management agents like Edge Processors, including onboarding, monitoring, and updates.

Add the data_management_agent role for the new user:

<img width="929" height="925" alt="image" src="https://github.com/user-attachments/assets/fe32b9d9-51cf-449a-a0eb-741fb4b50ae3" />

Click the **Selected Item(s)** checkbox to select both roles in the box on the right:

<img width="941" height="707" alt="image" src="https://github.com/user-attachments/assets/a555b91c-3291-4f0c-988a-186e176ecb16" />

Splunk's "Create a role for this user" option assigns predefined or custom roles to new users, defining their access and capabilities on the platform. Roles control user permissions and data accessibility.

Ensure the checkbox for **Require password change on next login** is selected so that the user will make a new password after they log in.  

Click **Create**:

<img width="1133" height="383" alt="image" src="https://github.com/user-attachments/assets/ed5f199c-a595-4bb2-8b50-01a74c8929a3" />

The new user has been created.  

## Log in to the New User Account

We will log in to the new user account.  

Click **Administrator** at the top of the window, then click **Logout**:

<img width="1130" height="383" alt="image" src="https://github.com/user-attachments/assets/c83da2de-3316-4730-88b5-54cd9ff04ae1" />

Log in to the new user account:

<img width="1141" height="285" alt="image" src="https://github.com/user-attachments/assets/ddecbbe9-2868-486d-a64f-5340a351d122" />

Enter a new password for the new user, then click **Save Password**:

<img width="1133" height="454" alt="image" src="https://github.com/user-attachments/assets/dfdc7570-97a0-450c-a77a-a0046a2cfdb5" />

This is how Splunk looks like after logging into the new user account:

<img width="1317" height="674" alt="image" src="https://github.com/user-attachments/assets/3fbfef81-6ff9-4b63-aec4-202e01d32fff" />


## What I Learned
- How to create a new user in Splunk Enterprise with just the right access to fit the principle of least privilege.
- Specific roles like data_management_agent let users handle things like onboarding and managing data agents without giving full admin rights.
- Navigating through Splunk’s settings to get to the Users section and how to set up a new user step-by-step.
- The importance of selecting the "Require password change on next login" option to keep things secure by forcing the new user to set their own password.
- What the Splunk interface looks like for a new user that logs in for the first time, which shows far less actions because they don't have admin privileges.

Overall, making a Splunk users is done in a easy and secure way that gives users nothing beyond the exact permissions they need.  
