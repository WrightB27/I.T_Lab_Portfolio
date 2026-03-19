# Section 4 – Device Hardening and Security Policies

This section documents the implementation of security and configuration policies for **Client01-IT** using Microsoft Intune. The objective is to demonstrate how endpoint hardening is enforced through centralized policy management in a cloud-native environment.

These configurations replace traditional Group Policy by applying security baselines, configuration profiles, and endpoint restrictions directly through Intune.

---

## 4.1 Security Objective

The goal of this section is to apply security controls to **Client01-IT** and verify that the device is configured according to organizational security standards.

Successful implementation must result in:

- Security policies assigned through Intune  
- Device configuration enforced on Client01-IT  
- Settings applied without manual intervention  
- Device aligned with a hardened security posture  

📸 **Screenshot Placeholder – Intune configuration profiles overview**  
`[INSERT SCREENSHOT – Devices > Configuration profiles]`

---

## 4.2 Policy Types Used

Microsoft Intune provides multiple policy types for device configuration and security enforcement.

### Selected Policy Types

- Configuration Profiles  
- Settings Catalog  
- Security Baselines  

These policies allow granular control over operating system behavior, user permissions, and security settings.

---

## 4.3 Create Configuration Profile

Configuration profiles are used to enforce device settings on managed endpoints.

### Steps

1. Sign in to Microsoft Intune Admin Center  
2. Navigate to:

   Devices → Windows → Configuration profiles  

3. Select:

   Create profile  

4. Configure:

- Platform: **Windows 10 and later**  
- Profile type: **Settings catalog**

📸 **Screenshot Placeholder – Create configuration profile screen**  
`[INSERT SCREENSHOT – Profile creation wizard]`

---

## 4.4 Configure Security Settings

Within the Settings Catalog, configure security-related settings.

### Example Security Settings

- Password policy enforcement  
- Account lockout threshold  
- Device restrictions  
- Microsoft Defender settings  
- Firewall configuration  

### Example Configuration

- Minimum password length: **[PLACEHOLDER – e.g., 12 characters]**  
- Password complexity: **Enabled**  
- Account lockout threshold: **[PLACEHOLDER – e.g., 5 attempts]**  
- Firewall: **Enabled**

These settings align the device with a baseline security posture.

📸 **Screenshot Placeholder – Settings catalog configuration**  
`[INSERT SCREENSHOT – Security settings configured in profile]`

---

## 4.5 Assign Configuration Profile

Policies must be assigned to apply to devices or users.

### Steps

1. Navigate to:

   Devices → Configuration profiles → [Profile Name]  

2. Select:

   Assignments  

3. Configure:

- Assignment target: **[PLACEHOLDER – User group or device group]**  
- Include **Client01-IT**

📸 **Screenshot Placeholder – Profile assignment**  
`[INSERT SCREENSHOT – Assignment configuration screen]`

---

## 4.6 Deploy Security Baseline

Security baselines provide preconfigured security settings aligned with Microsoft recommendations.

### Steps

1. Navigate to:

   Endpoint security → Security baselines  

2. Select:

   Windows 10/11 Security Baseline  

3. Create a new profile  

4. Configure baseline settings as required  

5. Assign to:

   **[PLACEHOLDER – Target group including Client01-IT]**

Security baselines simplify enforcement of best practices without manually configuring each setting.

📸 **Screenshot Placeholder – Security baseline configuration**  
`[INSERT SCREENSHOT – Security baseline profile settings]`

---

## 4.7 Monitor Policy Deployment

After assignment, policies are applied during device check-in.

### Steps

1. Navigate to:

   Devices → Windows → Client01-IT  

2. Review:

   Device configuration  

3. Verify:

- Policy status: **Succeeded**  
- Settings applied successfully  

📸 **Screenshot Placeholder – Policy status on device**  
`[INSERT SCREENSHOT – Device configuration status page]`

---

## 4.8 Validate Security Settings on Client01-IT

Local validation confirms that policies are enforced on the endpoint.

### Validation Steps

1. Log into **Client01-IT**  
2. Check:

- Password policy enforcement  
- Windows Defender status  
- Firewall status  

3. Attempt restricted actions if applicable to confirm enforcement  

📸 **Screenshot Placeholder – Local device security settings**  
`[INSERT SCREENSHOT – Windows Security showing applied settings]`

---

## 4.9 Security Outcome

At this stage, **Client01-IT** is configured with enforced security policies through Microsoft Intune.

This demonstrates:

- Centralized policy enforcement  
- Replacement of traditional Group Policy  
- Consistent device hardening  
- Alignment with enterprise security standards  

---

## 4.10 Section 4 Summary

This section demonstrated how to harden a Windows device using Microsoft Intune configuration profiles and security baselines.

Policies were created, assigned, and validated on **Client01-IT**, ensuring that security settings are enforced automatically and consistently.

This establishes a secure endpoint foundation and prepares the environment for compliance evaluation and Conditional Access enforcement in the next section.