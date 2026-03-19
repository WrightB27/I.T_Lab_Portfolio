# Section 6 – Windows LAPS Administration

This section documents the implementation of **Windows Local Administrator Password Solution (LAPS)** using Microsoft Intune. The objective is to demonstrate secure management of local administrator credentials on **Client01-IT** through centralized policy enforcement.

Windows LAPS provides automatic password rotation, secure storage, and controlled access to local administrator credentials, reducing the risk of credential compromise.

---

## 6.1 LAPS Objective

The goal of this section is to configure Windows LAPS on **Client01-IT** and validate that local administrator passwords are securely managed.

Successful implementation must result in:

- LAPS policy configured in Intune  
- Local administrator password automatically rotated  
- Password securely stored in Microsoft Entra ID  
- Controlled retrieval of password by authorized users  

📸 **Screenshot Placeholder – LAPS overview in Intune**  
`[INSERT SCREENSHOT – Endpoint security > Account protection]`

---

## 6.2 LAPS Overview

Windows LAPS replaces legacy solutions by integrating directly with Microsoft Entra ID and Intune.

### Key Features

- Automatic password rotation  
- Centralized password storage  
- Role-based access control  
- Audit logging for password retrieval  

This ensures that local administrator credentials are not reused across devices and are protected from unauthorized access.

---

## 6.3 Create LAPS Policy

### Steps

1. Sign in to Microsoft Intune Admin Center  
2. Navigate to:

   Endpoint security → Account protection  

3. Select:

   Create Policy  

4. Configure:

- Platform: **Windows 10 and later**  
- Profile: **Local admin password solution (Windows LAPS)**  

📸 **Screenshot Placeholder – Create LAPS policy screen**  
`[INSERT SCREENSHOT – LAPS policy creation wizard]`

---

## 6.4 Configure LAPS Settings

Define how passwords are managed on the device.

### Example Configuration

- Backup directory: **Microsoft Entra ID**  
- Password age (days): **[PLACEHOLDER – e.g., 7 or 30]**  
- Password length: **[PLACEHOLDER – e.g., 14 characters]**  
- Password complexity: **Enabled**  
- Administrator account name: **[PLACEHOLDER – Local admin account]**

These settings control password rotation frequency and complexity.

📸 **Screenshot Placeholder – LAPS configuration settings**  
`[INSERT SCREENSHOT – LAPS settings configured]`

---

## 6.5 Assign LAPS Policy

### Steps

1. Navigate to:

   Endpoint security → Account protection → [Policy Name]  

2. Select:

   Assignments  

3. Configure:

- Assignment target: **[PLACEHOLDER – User group or device group]**  
- Include **Client01-IT**

📸 **Screenshot Placeholder – LAPS assignment configuration**  
`[INSERT SCREENSHOT – Policy assigned to Client01-IT]`

---

## 6.6 Monitor LAPS Deployment

After assignment, the device applies the LAPS policy during check-in.

### Steps

1. Navigate to:

   Devices → Windows → Client01-IT  

2. Review:

   Device configuration or Endpoint security  

3. Verify:

- Policy status: **Succeeded**  
- LAPS settings applied  

📸 **Screenshot Placeholder – LAPS policy status**  
`[INSERT SCREENSHOT – Device showing LAPS policy applied]`

---

## 6.7 Retrieve Local Administrator Password

Once LAPS is active, the local administrator password can be securely retrieved.

### Steps

1. Open Microsoft Entra Admin Center  
2. Navigate to:

   Devices → All devices  

3. Select:

   **Client01-IT**

4. Locate:

   Local administrator password  

5. Select:

   Show local administrator password  

Access is restricted based on assigned roles.

📸 **Screenshot Placeholder – LAPS password retrieval**  
`[INSERT SCREENSHOT – Local admin password displayed]`

---

## 6.8 Validate Password Rotation

Confirm that password rotation is functioning as expected.

### Validation Steps

1. Retrieve the current password  
2. Wait for rotation interval or force policy refresh  
3. Retrieve password again  
4. Confirm password has changed  

This verifies that password rotation is active.

📸 **Screenshot Placeholder – Password rotation validation**  
`[INSERT SCREENSHOT – Password changed after rotation]`

---

## 6.9 LAPS Outcome

At this stage, **Client01-IT** is configured with Windows LAPS and is actively rotating local administrator passwords.

This demonstrates:

- Secure credential management  
- Elimination of static local admin passwords  
- Centralized password storage in Entra ID  
- Controlled administrative access  

---

## 6.10 Section 6 Summary

This section demonstrated the configuration and validation of Windows LAPS using Microsoft Intune.

The local administrator password on **Client01-IT** is now automatically rotated and securely stored in Microsoft Entra ID, reducing the risk of credential compromise.

This strengthens endpoint security and prepares the environment for update management and lifecycle control in the next section.