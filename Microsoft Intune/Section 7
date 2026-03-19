# Section 7 – Windows Update Management

This section documents the configuration of **Windows Update for Business (WUfB)** using Microsoft Intune to manage update deployment for **Client01-IT**. The objective is to demonstrate centralized control over operating system updates, ensuring devices remain secure and up to date without manual intervention.

Windows Update management through Intune allows administrators to define update rings, control deployment timing, and enforce update compliance across managed endpoints.

---

## 7.1 Update Management Objective

The goal of this section is to configure update policies for **Client01-IT** and validate that updates are deployed according to defined rules.

Successful implementation must result in:

- Update ring created in Intune  
- Policy assigned to Client01-IT  
- Device receiving update configuration  
- Update behavior controlled centrally  

📸 **Screenshot Placeholder – Update rings overview**  
`[INSERT SCREENSHOT – Devices > Windows > Update rings]`

---

## 7.2 Windows Update for Business Overview

Windows Update for Business (WUfB) provides cloud-based update management without requiring on-premises infrastructure such as WSUS.

### Key Capabilities

- Control update deployment timing  
- Define deferral periods  
- Manage restart behavior  
- Monitor update compliance  

This allows administrators to maintain device security while minimizing user disruption.

---

## 7.3 Create Update Ring Policy

### Steps

1. Sign in to Microsoft Intune Admin Center  
2. Navigate to:

   Devices → Windows → Update rings for Windows 10 and later  

3. Select:

   Create profile  

4. Configure:

- Name: **[PLACEHOLDER – Update Ring Name]**  
- Description: **[PLACEHOLDER – Description]**

📸 **Screenshot Placeholder – Create update ring profile**  
`[INSERT SCREENSHOT – Update ring creation screen]`

---

## 7.4 Configure Update Settings

Define how updates are deployed to the device.

### Example Configuration

- Servicing channel: **General Availability Channel**  
- Microsoft product updates: **Allow**  
- Windows drivers: **Allow or Block [based on lab preference]**  
- Quality update deferral: **[PLACEHOLDER – e.g., 7 days]**  
- Feature update deferral: **[PLACEHOLDER – e.g., 14 days]**  
- Automatic update behavior: **Auto install and restart at scheduled time**  

### Restart Settings

- Active hours: **[PLACEHOLDER – e.g., 8 AM to 5 PM]**  
- Restart notifications: **Enabled**

These settings control how and when updates are applied.

📸 **Screenshot Placeholder – Update ring configuration settings**  
`[INSERT SCREENSHOT – Update ring settings configured]`

---

## 7.5 Assign Update Ring Policy

### Steps

1. Navigate to:

   Devices → Windows → Update rings → [Policy Name]  

2. Select:

   Assignments  

3. Configure:

- Assignment target: **[PLACEHOLDER – User group or device group]**  
- Include **Client01-IT**

📸 **Screenshot Placeholder – Update ring assignment**  
`[INSERT SCREENSHOT – Policy assigned to Client01-IT]`

---

## 7.6 Monitor Update Deployment

After assignment, update policies are applied during device check-in.

### Steps

1. Navigate to:

   Devices → Windows → Client01-IT  

2. Review:

   Update status  

3. Verify:

- Update ring applied  
- Device receiving update policies  

📸 **Screenshot Placeholder – Device update status**  
`[INSERT SCREENSHOT – Client01-IT update configuration page]`

---

## 7.7 Validate Update Behavior on Client01-IT

Local validation confirms that update policies are enforced.

### Validation Steps

1. Log into **Client01-IT**  
2. Navigate to:

   Settings → Windows Update  

3. Confirm:

- Updates are managed by organization  
- Update schedule reflects policy  
- Restart behavior aligns with configured settings  

📸 **Screenshot Placeholder – Windows Update settings on device**  
`[INSERT SCREENSHOT – Windows Update showing managed by organization]`

---

## 7.8 Update Compliance Verification

Ensure the device remains compliant with update requirements.

### Steps

1. Navigate to:

   Reports → Windows updates  

2. Locate:

   **Client01-IT**

3. Verify:

- Update status: **Up to date or pending updates**  
- Compliance state aligned with policy  

📸 **Screenshot Placeholder – Update compliance report**  
`[INSERT SCREENSHOT – Update compliance dashboard]`

---

## 7.9 Update Management Outcome

At this stage, **Client01-IT** is managed through Windows Update for Business policies.

This demonstrates:

- Centralized update control  
- Automated patch management  
- Reduced dependency on on-prem infrastructure  
- Consistent update deployment across devices  

---

## 7.10 Section 7 Summary

This section demonstrated how to manage Windows updates using Microsoft Intune and Windows Update for Business.

Update rings were created, configured, and assigned to **Client01-IT**, ensuring that updates are deployed in a controlled and predictable manner.

This establishes a complete endpoint lifecycle by combining security, compliance, application management, and update control within a unified cloud-based management platform.