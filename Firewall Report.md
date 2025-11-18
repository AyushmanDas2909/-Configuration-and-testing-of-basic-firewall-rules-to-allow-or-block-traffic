# **Firewall Configuration Report \- TASK 4**

Date: November 2025

Operating System: Windows 10/11

**Objective:** To demonstrate fundamental firewall configuration, rule creation, and traffic filtering principles by blocking and testing a specific inbound port (23/Telnet).

## **1\. Environment and Tool Used**

The exercise was conducted on a **Windows 10/11** operating system. The primary tool utilized for configuring the firewall was the **Windows Defender Firewall with Advanced Security**, which was accessed using the command wf.msc in the Run dialog. For testing the rule's effectiveness, the user relied on **PowerShell**, specifically utilizing the Test-NetConnection cmdlet.

## **2\. Step-by-Step Procedure and Documentation**

The following steps outline the actions taken to implement, test, and remove a temporary firewall rule.

### **List Current Firewall Rules**

* **Action Performed:** The user navigated to the **Inbound Rules** section of the firewall console.  
* **Observation/Result:** An extensive default list of rules was observed, primarily consisting of "Allow" rules governing access for built-in Windows services and installed applications.

### **Add Rule to Block Inbound Traffic**

A **New Inbound Rule** was created using the Wizard with the following configuration details:

* **Rule Name:** TEST\_BLOCK\_TELNET\_23  
* **Rule Type:** Port  
* **Protocol:** TCP  
* **Port Number:** 23 (Telnet)  
* **Action:** Block the connection  
* **Profiles:** Domain, Private, and Public were all included.

### **Test the Rule**

This step used **PowerShell** to verify that the newly created blocking rule was active and functional.

* **Command Used:** The user executed Test-NetConnection \-ComputerName localhost \-Port 23\.  
* **Observation/Result:** The connection test resulted in TcpTestSucceeded : False.  
* **Conclusion:** The block rule was successfully verified, as the firewall prevented an attempted inbound TCP connection on Port 23 to the local machine.

### **Remove the Test Block Rule**

* **Action Performed:** The temporary rule, **TEST\_BLOCK\_TELNET\_23**, was located under **Inbound Rules** and successfully deleted.  
* **Conclusion:** The system firewall configuration was restored to its original state, ensuring network connectivity was not permanently impacted by the test rule.

## **3\. Summary of Firewall Functionality (Step 8\)**

A firewall serves as a critical security layer by acting as a filter between a host (computer) or private network and external traffic sources (like the internet). It operates by applying a set of defined rules to every packet of data that attempts to cross its boundary.

### **Key Filtering Components:**

1. **Direction:** Traffic is classified as **Inbound** (trying to reach the host) or **Outbound** (leaving the host).  
2. **Protocol & Port:** Rules typically specify the **Protocol** (e.g., TCP, UDP) and the **Port Number** (which identifies the specific service, like 80 for Web or 23 for Telnet).  
3. **Action:** The firewall consults its rules sequentially until a match is found, then applies the associated action: **Allow** (permit the traffic) or **Block/Deny** (discard the traffic).

The exercise clearly demonstrated this process: the firewall intercepted the inbound connection attempt to **TCP Port 23** and, because the specific **Block** rule was explicitly listed, the traffic was dropped before it could reach the target application, thus enforcing the security policy.