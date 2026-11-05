# Internal KB: Standard Operating Procedure for User Password Resets

**Article ID:** KB001425  
**Target Audience:** IT Support Tier 1  
**Last Updated:** November 2026  

## Issue Description
An end-user is locked out of their primary corporate account or requires a manual password reset due to an expired credential or forgotten password.

## Standard Operating Procedure (SOP)

### 1. Identity Verification (Mandatory Security Step)
Before altering any account credentials, you must positively verify the user's identity to prevent unauthorized access or social engineering attacks.
* **Internal Employee:** Verify via an out-of-band factor (e.g., call their registered corporate mobile number, verify their manager, or check their employee ID number against the HR database).
* **Never** send a temporary password to a personal email address unless it matches the verified record in the HR platform.

### 2. Active Directory / Entra ID Reset Procedure
1. Open the **Microsoft Entra admin center** or **Active Directory Users and Computers (ADUC)**.
2. Search for the user using their unique User Principal Name (UPN) or corporate email address.
3. Select the user profile and click **Reset Password**.
4. Generate a secure, complex temporary password meeting corporate password complexity requirements (minimum 14 characters, numbers, and symbols).
5. Ensure the box **"Require user to change password at next sign-in"** is explicitly checked.

### 3. Clear Account Lockouts
If the user repeatedly entered the wrong password, their account may be locked out at the domain controller level.
* In the user's account properties, navigate to the **Account** tab.
* Check if the account is locked and click **Unlock Account** -> **Apply**.

### 4. Direct the User to Self-Service Password Reset (SSPR)
To reduce future help desk volume, instruct the user to register for the corporate self-service portal:
* Provide the user with the registration link: `https://aka.ms`
* Walk them through configuring their alternative email and phone number for future automated recovery.

## Escalation Path
If the account remains locked or the user encounters a "Substrate Account Error" during sync, escalate the ticket to the **Identity and Access Management (IAM) Team**.
