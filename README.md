# **🛡️ Windows Firewall Security Practice (Port Blocking Demonstration)**

This repository contains the documentation and evidence for a practical exercise demonstrating basic firewall configuration on a Windows operating system. The objective was to understand how to implement, verify, and remove a rule to block specific inbound network traffic.

## **🎯 Project Objective**

The primary goal of this exercise was to practice fundamental network security policy enforcement by:

1. Listing the current firewall configuration.  
2. Creating a temporary **Inbound Rule** to explicitly block all connections to a non-standard service port (specifically **TCP Port 23**, commonly used for Telnet).  
3. Verifying the effectiveness of the block rule using a command-line utility.  
4. Restoring the original system state by deleting the test rule.

## **💻 Environment and Tools**

* **Operating System:** Windows 10 / Windows 11  
* **Firewall Management:** Windows Defender Firewall with Advanced Security (wf.msc)  
* **Testing Utility:** PowerShell (Test-NetConnection cmdlet)

## **📄 Documentation and Evidence Files**

This repository contains five primary files documenting the procedure, observations, and results:

* [**firewall\_report.md**](https://www.google.com/search?q=./firewall_report.md)  
  * **Description:** This is the **Comprehensive Report** and **Primary Deliverable**. It details the step-by-step procedure, configuration actions, technical observations, and a theoretical summary of how the firewall filters network traffic.  
* **current\_rules.txt**  
  * **Description:** A snapshot (text dump) of the system's inbound rules *before* the test rule was initially implemented.  
* **demo\_rule\_properties.png**  
  * **Description:** Visual evidence showcasing the detailed properties, configuration, and settings of the new blocking rule (**Demo Rule Properties**).  
* **demo\_rule\_deployment.png**  
  * **Description:** Visual evidence showing the rule successfully created and active in the Inbound Rules list (**Demo Rule Deployment**).  
* **demo\_rule\_testing\_powershell.png**  
  * **Description:** Visual evidence confirming rule validation using **PowerShell's Test-NetConnection** command, demonstrating that the block is working (**Demo Rule Testing using PowerShell**).

## **🔗 How to Use This Repo**

To replicate this exercise, refer to the step-by-step instructions detailed in the [firewall\_report.md](https://www.google.com/search?q=./firewall_report.md) file.