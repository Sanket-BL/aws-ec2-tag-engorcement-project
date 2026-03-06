
# AWS EC2 Tag Enforcement Project

## Project Overview

This project demonstrates how to enforce mandatory tagging for EC2 instances using AWS IAM policies.

Organizations often require resource tags for:

- Cost management
- Resource identification
- Ownership tracking
- Governance

This project prevents launching EC2 instances unless required tags are provided.

---

## Required Tags

| Tag Key | Description |
|------|------|
| Name | Instance owner name |
| emailID | Owner email |
| phoneNo | Contact number |
| Place | Location |

---

## Architecture

IAM User  
↓  
Custom IAM Policy (Tag Enforcement)  
↓  
EC2 Launch Request  
↓  
Policy Validation  
↓  
Instance Created Only If Tags Exist

---

## Implementation Steps

### 1. Create IAM User
Create a user with programmatic or console access.

### 2. Attach Permissions

Attach the following policy:

AmazonEC2FullAccess

### 3. Create Custom IAM Policy

Policy denies EC2 instance creation if required tags are missing.

### 4. Attach Policy to IAM User

Attach the custom policy to the IAM user.

---

## Testing

### Case 1 – Launch Without Tags

Result:
