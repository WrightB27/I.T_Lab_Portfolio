# Section 3 – Application Deployment

This section documents the deployment of applications to **Client01-IT** using Microsoft Intune. The objective is to demonstrate centralized application management in a cloud-native environment, replacing traditional manual installation methods.

Application deployment in Intune allows administrators to deliver software consistently, enforce installation requirements, and monitor deployment status across managed endpoints.

---

## 3.1 Deployment Objective

The goal of this section is to successfully deploy an application to **Client01-IT** and validate installation through the Intune admin center and the endpoint itself.

Successful deployment must result in:

- Application visible in Intune  
- Application assigned to the correct user or device  
- Application installed on Client01-IT  
- Installation status reported in Intune  

📸 **Screenshot Placeholder – Intune Apps overview page**  
`[INSERT SCREENSHOT – Apps > All apps view]`

---

## 3.2 Application Type Selection

Microsoft Intune supports multiple application deployment types. For this lab, a **Windows Win32 application** is used to simulate real enterprise deployment scenarios.

### Selected Application Type

- App Type: **Windows app (Win32)**
- Deployment Method: **Required assignment**
- Target Device: **Client01-IT**

### Application Details

- Application Name: **[PLACEHOLDER – Example: Google Chrome / 7-Zip / Notepad++]**
- Source File: **[PLACEHOLDER – .intunewin package]**
- Install Command: **[PLACEHOLDER – install command]**
- Uninstall Command: **[PLACEHOLDER – uninstall command]**

Win32 applications are selected because they provide flexibility, support custom install commands, and represent real-world enterprise software deployment.

---

## 3.3 Prepare Application Package

Before deployment, the application must be packaged into the **.intunewin** format.

### Steps

1. Download the application installer  
2. Download the Microsoft Win32 Content Prep Tool  
3. Run the tool:

```cmd
IntuneWinAppUtil.exe

Provide:

- Source folder  
- Setup file  
- Output folder  

Generate the `.intunewin` file.
```

📸 **Screenshot Placeholder – Win32 content prep tool output**  
`[INSERT SCREENSHOT – Successful .intunewin creation]`

## 3.4 Upload Application to Intune

### Steps

1. Sign in to Microsoft Intune Admin Center  
2. Navigate to:

   Apps → Windows → Add  

3. Select:

   Windows app (Win32)  

4. Upload the `.intunewin` file  

5. Configure application information:

- Name: **[PLACEHOLDER – App Name]**  
- Description: **[PLACEHOLDER – App Description]**  
- Publisher: **[PLACEHOLDER – Publisher]**

📸 **Screenshot Placeholder – App upload screen**  
`[INSERT SCREENSHOT – Win32 app upload interface]`

---

## 3.5 Configure Application Settings

After uploading, configure installation behavior.

### Program Settings

- Install command: **[PLACEHOLDER – install command]**  
- Uninstall command: **[PLACEHOLDER – uninstall command]**  
- Install behavior: **System**

### Requirements

- Operating system: **Windows 10/11**  
- Architecture: **[PLACEHOLDER – x64/x86]**

### Detection Rules

Detection rules confirm whether the application is installed.

Example:

- File path: **[PLACEHOLDER – Program Files path]**  
- Detection method: **File or registry**

### Return Codes

Use default return codes unless customization is required.

📸 **Screenshot Placeholder – App configuration settings**  
`[INSERT SCREENSHOT – Program and detection rules configuration]`

---

## 3.6 Assign Application to Client01-IT

Applications must be assigned to a target before deployment.

### Steps

1. Navigate to:

   Apps → All apps → **[Application Name]**  

2. Select:

   Assignments  

3. Configure assignment:

- Assignment type: **Required**  
- Target: **[PLACEHOLDER – User group or device group]**

For this lab, the assignment should target the user associated with **Client01-IT** or the device directly.

📸 **Screenshot Placeholder – Assignment configuration**  
`[INSERT SCREENSHOT – Assignment set to Required]`

---

## 3.7 Monitor Deployment Status

After assignment, Intune begins deployment during device check-in.

### Monitoring Steps

1. Navigate to:

   Apps → Monitor → App install status  

2. Locate:

   **[Application Name]**

3. Verify:

- Install status: **Installed**  
- Device: **Client01-IT**

📸 **Screenshot Placeholder – App install status dashboard**  
`[INSERT SCREENSHOT – Deployment status showing Installed]`

---

## 3.8 Validate Installation on Client01-IT

Verification on the endpoint confirms that deployment completed successfully.

### Validation Steps

1. Log into **Client01-IT**  
2. Confirm application is installed:

- Start Menu  
- Installed programs list  

3. Launch the application to confirm functionality  

📸 **Screenshot Placeholder – Application installed on Client01-IT**  
`[INSERT SCREENSHOT – Application visible on device]`

---

## 3.9 Deployment Outcome

At this stage, **Client01-IT** has successfully received and installed an application through Microsoft Intune.

This demonstrates:

- Centralized software deployment  
- Automated installation without manual intervention  
- Visibility into deployment status  
- Consistent application delivery  

---

## 3.10 Section 3 Summary

This section demonstrated the deployment of a Win32 application to **Client01-IT** using Microsoft Intune.

The process included packaging the application, uploading it to Intune, configuring installation parameters, assigning it to a target, and validating successful deployment.

This establishes the foundation for managing enterprise applications through Intune and prepares the environment for enforcing security policies and compliance controls in the next section.