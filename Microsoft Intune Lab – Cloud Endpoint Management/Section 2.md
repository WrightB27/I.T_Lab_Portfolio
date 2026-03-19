# Section 2 – Device Enrollment with Autopilot

This section documents the enrollment of **Client01-IT** into Microsoft Intune using a cloud-native approach with Microsoft Entra ID. The process demonstrates how a Windows device is onboarded into enterprise management, allowing centralized control over configuration, security, applications, and updates.

The enrollment process is designed to reflect a real administrative workflow rather than a basic walkthrough. Each step validates that the device is properly registered, joined, and managed within the Microsoft ecosystem.

---

## 2.1 Enrollment Objective

The objective of this section is to successfully onboard **Client01-IT** into Microsoft Intune and confirm that the device is fully managed.

Successful enrollment must result in:

- Device joined to Microsoft Entra ID  
- Device enrolled in Microsoft Intune (MDM)  
- Device visible in Intune admin center  
- Device assigned to the correct user  
- Device able to receive policies and applications  

📸 **Screenshot Placeholder – Intune Devices overview page**  
`[INSERT SCREENSHOT – Devices > All devices showing Client01-IT]`

---

## 2.2 Enrollment Method Selection

This lab uses a **cloud-native enrollment method**.

### Selected Method

- Join Type: **Microsoft Entra ID Join**
- Enrollment Type: **Automatic MDM Enrollment**
- Device Type: **Windows 10/11**
- Ownership: **[PLACEHOLDER – Corporate or Personal]**

Windows Autopilot is referenced in this section as part of the lab structure. For this implementation, enrollment is performed using a direct Entra ID join to simulate an out-of-box experience without requiring full Autopilot profile deployment.

This approach allows validation of:

- Device registration  
- MDM enrollment  
- Policy assignment readiness  

📸 **Screenshot Placeholder – Entra ID join screen during setup**  
`[INSERT SCREENSHOT – Windows setup screen showing “Set up for work or school”]`

---

## 2.3 Prerequisites

Before enrolling Client01-IT, the following prerequisites must be confirmed.

### Tenant Requirements

- Microsoft Intune is active  
- Microsoft Entra ID is configured  
- Microsoft 365 licensing assigned  

### Required Accounts

- **[PLACEHOLDER – Global Admin account]**  
- **[PLACEHOLDER – Enrollment test user account]**

The test user must have a valid Microsoft 365 license that includes Intune.

### Device Requirements

- Device Name: **Client01-IT**  
- OS Version: **[PLACEHOLDER – Windows version]**  
- Internet Access: Required  
- Clean state: Fresh install or reset recommended  

---

## 2.4 Configure Automatic MDM Enrollment

Automatic enrollment ensures that devices joined to Microsoft Entra ID are enrolled into Intune without manual intervention.

### Steps

1. Sign in to Microsoft Intune Admin Center  
2. Navigate to:

   Devices → Enroll devices → Automatic enrollment  

3. Configure MDM user scope:

   - Set to **All**  
   - Or **Some** if using scoped deployment  

4. Save configuration  

This ensures that when Client01-IT joins Entra ID, it is automatically enrolled into Intune.

📸 **Screenshot Placeholder – Automatic MDM enrollment configuration**  
`[INSERT SCREENSHOT – MDM user scope set to All]`

---

## 2.5 Enroll Client01-IT into Entra ID

The device is enrolled during Windows setup or through manual join.

### Enrollment Steps (Manual Join Method)

1. On Client01-IT, open:

   Settings → Accounts → Access work or school  

2. Select:

   Connect  

3. Choose:

   Join this device to Microsoft Entra ID  

4. Enter:

   **[PLACEHOLDER – Enrollment user account]**

5. Complete authentication  

6. Confirm device join  

After completion, the device is:

- Joined to Microsoft Entra ID  
- Automatically enrolled into Intune  

📸 **Screenshot Placeholder – Device successfully joined to Entra ID**  
`[INSERT SCREENSHOT – Access work or school showing Connected to Entra ID]`

---

## 2.6 Verify Device Enrollment in Intune

After enrollment, verification is required to confirm that the device is fully managed.

### Verification Steps

1. Open Microsoft Intune Admin Center  
2. Navigate to:

   Devices → Windows → All devices  

3. Locate:

   **Client01-IT**

4. Confirm the following:

- Device status: **Managed**  
- MDM: **Microsoft Intune**  
- Ownership: **[PLACEHOLDER – Corporate/Personal]**  
- Compliance state: **[Expected: Not evaluated or Compliant after policy assignment]**

📸 **Screenshot Placeholder – Device details in Intune**  
`[INSERT SCREENSHOT – Client01-IT device overview page]`

---

## 2.7 Verify Device in Microsoft Entra ID

Confirm that the device is registered correctly in Entra ID.

### Steps

1. Open Microsoft Entra Admin Center  
2. Navigate to:

   Devices → All devices  

3. Locate:

   **Client01-IT**

4. Validate:

- Join type: **Microsoft Entra joined**  
- Registered owner: **[PLACEHOLDER – User account]**  
- Device status: **Enabled**

📸 **Screenshot Placeholder – Entra device record**  
`[INSERT SCREENSHOT – Client01-IT listed in Entra ID]`

---

## 2.8 Local Device Validation

Validation on the endpoint confirms that enrollment completed successfully.

### Commands

Open Command Prompt and run:

```cmd
dsregcmd /status
```
### Expected Results

- AzureAdJoined: **YES**  
- MDMUrl: **Present**  
- TenantName: **[PLACEHOLDER – Tenant name]**

This confirms that the device is properly joined and enrolled.

📸 **Screenshot Placeholder – dsregcmd output**  
`[INSERT SCREENSHOT – dsregcmd /status showing AzureAdJoined = YES]`

---

## 2.9 Enrollment Outcome

At this stage, **Client01-IT** is:

- Joined to Microsoft Entra ID  
- Enrolled into Microsoft Intune  
- Assigned to a licensed user  
- Ready to receive policies, applications, and configurations  

This establishes the foundation required for all remaining sections in the lab.

---

## 2.10 Section 2 Summary

This section demonstrated the enrollment of **Client01-IT** into Microsoft Intune using a cloud-native Microsoft Entra ID join.

The device is now fully managed and visible in both Intune and Entra ID. Enrollment enables centralized control over configuration, security policies, application deployment, compliance enforcement, and update management.

This completes the onboarding phase of the lab and prepares the environment for policy deployment and advanced configuration in the following sections.