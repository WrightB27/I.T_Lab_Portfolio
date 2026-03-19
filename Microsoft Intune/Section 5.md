# Section 5 – Compliance Enforcement with Conditional Access

This section documents the implementation of compliance policies and Conditional Access to control access to resources based on the security state of **Client01-IT**.

The objective is to demonstrate how Microsoft Intune and Microsoft Entra ID work together to enforce security requirements before granting access to cloud resources.

---

## 5.1 Compliance Objective

The goal of this section is to ensure that only compliant devices are allowed to access organizational resources.

Successful implementation must result in:

- Compliance policy assigned to Client01-IT  
- Device evaluated for compliance status  
- Conditional Access policy enforcing compliance  
- Access restricted for non-compliant devices  

📸 **Screenshot Placeholder – Compliance policies overview**  
`[INSERT SCREENSHOT – Devices > Compliance policies]`

---

## 5.2 Create Compliance Policy

Compliance policies define the rules that a device must meet to be considered secure.

### Steps

1. Sign in to Microsoft Intune Admin Center  
2. Navigate to:

   Devices → Compliance policies → Policies  

3. Select:

   Create Policy  

4. Configure:

- Platform: **Windows 10 and later**

📸 **Screenshot Placeholder – Create compliance policy screen**  
`[INSERT SCREENSHOT – Compliance policy creation wizard]`

---

## 5.3 Configure Compliance Settings

Define the security requirements for the device.

### Example Compliance Settings

- Require BitLocker encryption  
- Require secure boot  
- Require minimum OS version  
- Require Microsoft Defender enabled  

### Example Configuration

- BitLocker: **Required**  
- Secure Boot: **Required**  
- Minimum OS version: **[PLACEHOLDER – Version]**  
- Microsoft Defender Antivirus: **Required**

These settings determine whether the device is considered compliant.

📸 **Screenshot Placeholder – Compliance settings configuration**  
`[INSERT SCREENSHOT – Compliance policy settings]`

---

## 5.4 Assign Compliance Policy

### Steps

1. Navigate to:

   Devices → Compliance policies → [Policy Name]  

2. Select:

   Assignments  

3. Configure:

- Assignment target: **[PLACEHOLDER – User group or device group]**  
- Include **Client01-IT**

📸 **Screenshot Placeholder – Compliance policy assignment**  
`[INSERT SCREENSHOT – Assignment configuration screen]`

---

## 5.5 Verify Device Compliance Status

After assignment, Intune evaluates the device.

### Steps

1. Navigate to:

   Devices → Windows → Client01-IT  

2. Review:

   Compliance  

3. Confirm:

- Compliance status: **Compliant** or **Not compliant**  
- Policy applied successfully  

📸 **Screenshot Placeholder – Device compliance status**  
`[INSERT SCREENSHOT – Client01-IT compliance page]`

---

## 5.6 Configure Conditional Access Policy

Conditional Access enforces access control based on compliance.

### Steps

1. Sign in to Microsoft Entra Admin Center  
2. Navigate to:

   Protection → Conditional Access  

3. Select:

   Create new policy  

4. Configure:

- Name: **[PLACEHOLDER – Policy Name]**  
- Users: **[PLACEHOLDER – Target users]**  
- Target resources: **All cloud apps** or specific apps  

📸 **Screenshot Placeholder – Conditional Access policy creation**  
`[INSERT SCREENSHOT – Conditional Access policy wizard]`

---

## 5.7 Define Access Controls

Configure enforcement rules.

### Grant Controls

- Require device to be marked as compliant  

### Additional Options

- Require multi-factor authentication (optional)  

This ensures only compliant devices can access resources.

📸 **Screenshot Placeholder – Grant controls configuration**  
`[INSERT SCREENSHOT – Require compliant device setting]`

---

## 5.8 Test Conditional Access Enforcement

Validation confirms that access policies are working as expected.

### Test Scenarios

- Compliant device access → Allowed  
- Non-compliant device access → Blocked  

### Steps

1. Attempt sign-in from **Client01-IT**  
2. Confirm access is granted when compliant  
3. Modify compliance state (if testing) and verify restriction  

📸 **Screenshot Placeholder – Conditional Access test result**  
`[INSERT SCREENSHOT – Access allowed or blocked message]`

---

## 5.9 Compliance and Access Outcome

At this stage, **Client01-IT** is evaluated for compliance and subject to Conditional Access policies.

This demonstrates:

- Integration between Intune and Entra ID  
- Real-time compliance evaluation  
- Access control based on device state  
- Enforcement of security requirements  

---

## 5.10 Section 5 Summary

This section demonstrated how to enforce compliance and control access using Microsoft Intune and Conditional Access.

Compliance policies were created and assigned, and Conditional Access was configured to require compliant devices for resource access.

This ensures that only secure and properly configured devices can access organizational resources, strengthening the overall security posture of the environment.