# Section 1 – Lab Overview and Architecture

This section defines the architecture, scope, and technical design of the Microsoft Intune lab environment. The lab is built to demonstrate modern cloud-based endpoint management using Microsoft Entra ID and Microsoft Intune, with **Client01-IT** serving as the primary managed Windows endpoint. The objective is to show a realistic administrative workflow that covers enrollment, configuration, application delivery, security enforcement, update control, and troubleshooting in a structured lab suitable for a GitHub portfolio.

## 1.1 Lab Objective

The purpose of this lab is to simulate a small enterprise endpoint management environment that uses Microsoft cloud services instead of traditional on-premises Group Policy as the primary management method.

This lab was designed to validate the following capabilities:

- Microsoft Entra ID device identity
- Intune-based Windows device management
- Policy-based endpoint hardening
- Application deployment from Intune
- Compliance evaluation and Conditional Access enforcement
- Windows LAPS administration
- Windows Update for Business configuration
- Administrative monitoring and troubleshooting

Unlike a basic tenant walkthrough, this lab is structured as a full implementation project. Each section documents not only what was configured, but also why the configuration supports enterprise management standards.

📸 **Screenshot Placeholder – Repository cover image or lab title banner**  
`[INSERT SCREENSHOT – GitHub repo banner or section title image]`

---

## 1.2 Management Model

This lab uses a **cloud-native management model**.

The enrolled endpoint, **Client01-IT**, is configured as a **Microsoft Entra ID joined** Windows device and is managed through **Microsoft Intune**. This design was chosen to align the lab with current Microsoft endpoint administration practices and with the type of configuration expected in modern SMB and enterprise cloud environments.

### Selected Management Approach

- Identity Provider: **Microsoft Entra ID**
- MDM Platform: **Microsoft Intune**
- Primary Test Device: **Client01-IT**
- Join Type: **Entra ID Joined**
- Management Method: **Cloud-native MDM**
- Operating System: **[PLACEHOLDER – Windows edition used on Client01-IT]**
- Licensing Baseline: **Microsoft 365 Business Premium** `[confirm exact subscription if different]`

This architecture intentionally avoids hybrid dependency for the primary endpoint. Client01-IT is not presented as a domain-managed device in this repo section. The endpoint is treated as a cloud-managed system so that policy, compliance, updates, and application deployment are all administered from Intune.

📸 **Screenshot Placeholder – Microsoft Intune admin center home page**  
`[INSERT SCREENSHOT – Intune admin center overview dashboard]`

📸 **Screenshot Placeholder – Microsoft Entra admin center showing device join state**  
`[INSERT SCREENSHOT – Client01-IT listed as Microsoft Entra joined]`

---

## 1.3 Lab Environment Components

The lab environment consists of a cloud management plane and a single primary Windows endpoint used for testing administrative actions.

### Core Components

**Microsoft Entra ID**  
Provides cloud identity, device registration, authentication, and access control evaluation.

**Microsoft Intune**  
Provides mobile device management, policy deployment, application delivery, compliance monitoring, Windows LAPS administration, and update management.

**Client01-IT**  
Serves as the primary enrolled endpoint. This system is used to validate enrollment behavior, policy assignment, app installation, compliance results, update deployment, and administrative troubleshooting.

**Microsoft 365 Business Premium**  
Provides the licensing foundation required for Intune, Entra ID capabilities, security features, and endpoint administration features used throughout the lab.

### Optional Supporting Lab Infrastructure

Your earlier lab environment also included a Windows Server infrastructure built around **DC01**, **CorpNet.local**, internal DNS, and DHCP. That environment established a strong infrastructure baseline and showed traditional directory services design. For this Intune project, however, the management focus shifts to **Entra ID + Intune**, with **Client01-IT** acting as the cloud-managed endpoint rather than a domain-managed client.

📸 **Screenshot Placeholder – Devices view in Intune showing Client01-IT**  
`[INSERT SCREENSHOT – Devices > Windows > Client01-IT]`

---

## 1.4 Architecture Design Rationale

The lab architecture was designed around one clear goal: demonstrate practical endpoint administration using Microsoft’s modern management stack in a way that is easy to review, replicate, and present.

### Why Entra ID and Intune were selected

Traditional Active Directory and Group Policy remain important in many environments, but Microsoft endpoint administration is increasingly centered on cloud identity and MDM-based control. A cloud-managed design allows the lab to demonstrate the administrative path most relevant to current Intune roles and MD-102-aligned skills.

### Why Client01-IT was selected as the primary device

Client01-IT is used as the dedicated test endpoint so that all device lifecycle actions can be documented against one consistent system. This keeps the lab focused and makes it easier to show cause-and-effect relationships between assigned policies and endpoint results.

### Why a single primary endpoint is still valid for an advanced lab

A single well-documented endpoint can still support advanced testing when the implementation includes:

- identity join validation
- policy targeting
- compliance evaluation
- access control enforcement
- application deployment
- update ring behavior
- local administrator management
- troubleshooting evidence

This approach produces a cleaner GitHub portfolio project than a loosely documented multi-device setup.

---

## 1.5 High-Level Architecture

The following flow represents the management relationship used in the lab:

```text
Administrator
    │
    ▼
Microsoft Intune Admin Center
    │
    ├── Configuration Profiles
    ├── Compliance Policies
    ├── Application Deployment
    ├── Windows LAPS
    ├── Update Rings
    └── Device Monitoring
    │
    ▼
Microsoft Entra ID
    │
    ├── Device Identity
    ├── User Authentication
    └── Conditional Access Evaluation
    │
    ▼
Client01-IT
    │
    ├── Entra ID Joined
    ├── Intune Enrolled
    ├── Receives Policies
    ├── Receives Applications
    ├── Reports Compliance State
    └── Receives Update Controls
    ```
📸 **Screenshot Placeholder – Topology diagram for Intune lab**  
`[INSERT SCREENSHOT OR DIAGRAM – High-level architecture showing Admin > Intune > Entra ID > Client01-IT]`

```

## 1.6 Administrative Scope of the Lab

The repository is organized into eight sections. The structure keeps the project readable while covering the core areas of Microsoft Intune administration.

### Section layout

1. Lab Overview and Architecture  
2. Device Enrollment with Autopilot  
3. Application Deployment  
4. Device Hardening and Security Policies  
5. Compliance Enforcement with Conditional Access  
6. Windows LAPS Administration  
7. Windows Update Management  
8. Automation, Monitoring, and Troubleshooting  

This section establishes the foundation for the remaining sections and defines how the environment is structured before configuration begins.

---

## 1.7 Planned Administrative Workflow

The lab follows a structured endpoint lifecycle.

### Workflow

**Stage 1: Establish cloud identity and management platform**  
A Microsoft tenant with the required licensing supports Microsoft Entra ID and Intune.

**Stage 2: Prepare and enroll Client01-IT**  
The device is prepared for cloud enrollment and joined to Microsoft Entra ID. Enrollment places the device under Intune management.

**Stage 3: Configure management controls**  
Policies, security baselines, compliance rules, and update settings are assigned.

**Stage 4: Validate results**  
The device is reviewed in the Intune admin center to confirm check-in status, assignment results, and compliance state.

**Stage 5: Document results**  
Screenshots and validation steps are captured for GitHub.

This workflow reflects a real administrative deployment process.

---

## 1.8 Lab Assumptions and Required Placeholders

The following values are required for accuracy in later sections.

### Required placeholders

- **[PLACEHOLDER – Tenant name]**  
- **[PLACEHOLDER – Primary lab admin account]**  
- **[PLACEHOLDER – Enrollment test user account]**  
- **[PLACEHOLDER – Windows edition on Client01-IT]**  
- **[PLACEHOLDER – Device ownership type (Corporate or Personal)]**  
- **[PLACEHOLDER – Naming standard if different from Client01-IT]**  

---

## 1.9 Validation Goals for Section 1

This section must establish that the lab is structured and credible.

### Section validation points

- Defined enterprise management objective  
- Microsoft Entra ID and Intune used as the primary stack  
- Client01-IT identified as the managed endpoint  
- Clear implementation structure  
- Designed for repeatable administrative testing  

📸 **Screenshot Placeholder – Section summary evidence image**  
`[INSERT SCREENSHOT – Intune tenant view or Client01-IT device record]`

---

## 1.10 Section 1 Summary

This lab demonstrates cloud-based endpoint management using Microsoft Entra ID, Microsoft Intune, and the Windows device Client01-IT.

The environment supports device enrollment, policy enforcement, application deployment, compliance evaluation, local administrator management, update control, and troubleshooting.

Each section builds on the same endpoint and tenant to show a complete management workflow in a structured GitHub project.   