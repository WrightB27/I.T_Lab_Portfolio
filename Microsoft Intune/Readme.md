# Microsoft Intune Lab – Cloud Endpoint Management

This repository documents a complete Microsoft Intune lab designed to demonstrate modern cloud-based endpoint management using **Microsoft Entra ID** and **Microsoft Intune**. The project focuses on managing a Windows device, **Client01-IT**, through its full lifecycle from enrollment to ongoing maintenance.

The lab is structured to reflect real administrative workflows and is intended for use as a technical portfolio project.

---

## Lab Overview

This lab demonstrates how to manage Windows endpoints without reliance on traditional on-premises infrastructure. All management functions are performed through Microsoft Intune and Microsoft Entra ID.

### Core Capabilities Demonstrated

- Device enrollment with Microsoft Entra ID  
- Application deployment using Win32 apps  
- Device hardening through configuration profiles and security baselines  
- Compliance enforcement with Conditional Access  
- Local administrator password management using Windows LAPS  
- Windows Update for Business configuration  
- Monitoring and troubleshooting using Intune tools  

---

## Lab Architecture

The environment follows a cloud-native design where management is centralized in Microsoft Intune and identity is handled by Microsoft Entra ID.

**Primary Components**

- Microsoft Entra ID  
- Microsoft Intune  
- Windows Endpoint: **Client01-IT**  
- Microsoft 365 Licensing: **[PLACEHOLDER – Tenant subscription]**

All configurations are applied from the Intune admin center and enforced on the endpoint through policy-based management.

---

## Lab Structure

The repository is organized into eight sections that align with the endpoint management lifecycle:

1. Lab Overview and Architecture  
2. Device Enrollment with Autopilot  
3. Application Deployment  
4. Device Hardening and Security Policies  
5. Compliance Enforcement with Conditional Access  
6. Windows LAPS Administration  
7. Windows Update Management  
8. Automation, Monitoring, and Troubleshooting  

Each section includes configuration steps, validation procedures, and supporting screenshots.

---

## Technologies Used

- Microsoft Intune  
- Microsoft Entra ID  
- Windows 10/11  
- Windows LAPS  
- Windows Update for Business  

---

## Key Outcomes

This lab demonstrates the ability to:

- Manage endpoints using a cloud-native approach  
- Apply and enforce security policies through Intune  
- Deploy applications in a controlled manner  
- Restrict access based on device compliance  
- Secure local administrator credentials  
- Control update deployment and compliance  
- Monitor and troubleshoot managed devices  

---

## Prerequisites

To replicate this lab, the following are required:

- Microsoft 365 subscription with Intune  
- Microsoft Entra ID tenant  
- Windows device for enrollment  
- Administrative access to Intune and Entra ID  

---

## Usage

This repository is intended for:

- Demonstrating Microsoft Intune administration skills  
- Learning cloud-based endpoint management  
- Serving as a reference for similar lab implementations  

Each section can be followed independently, but the full sequence provides a complete endpoint lifecycle.

---

## Notes

- Replace placeholders with actual tenant and environment details before publishing  
- Ensure screenshots reflect your deployed environment  
- Maintain consistent naming conventions across all sections  

---

## Author

**[Brendan Wright]**

---

## License

This project is for educational and portfolio purposes.