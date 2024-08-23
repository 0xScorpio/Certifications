# Oveview of Defender XDR

![image](https://github.com/user-attachments/assets/0801b78a-b6c4-4f0d-83c7-42a14de71781)

Extended Detection and Response (XDR) combines signals from:
- endpoints
- identity
- email
- applications

## Detection Process

![image](https://github.com/user-attachments/assets/90e62f23-56c4-4155-bb14-36d7aa813964)

The victim receives a malicious email on a personal email account not protected by Microsoft Defender for Office 365 (MDO) or a USB drive and opens the attachment. Once the attachment opens, Microsoft Defender for Endpoints (MDE) detects this attack, raises an alert to security operations, and provides details about the threat to the Security team. Disable user access from device while infected - MDE communicates to Intune that the risk level on this endpoint has changed. An Intune Compliance Policy configured with an MDE risk level severity is triggered and marks the account as noncompliant with organizations policy. The Conditional Access created in Microsoft Entra ID blocks user access to apps.

## Access Restriction

Conditional Access knows about device risk because Microsoft Defender for Endpoint (MDE) notified Intune, which then updated the compliance status of the device in Microsoft Entra ID.
During this time, the user is restricted from accessing corporate resources. This applies to all new resource requests and blocks any current access to resources that support continuous access evaluation (CAE). People are able to do general internet productivity tasks, like research YouTube, Wikipedia, and anything else that doesn’t require corporate authentication, but won’t have access to corporate resources.

## Access Restoration

Once the threat has been remediated and cleaned up, MDE triggers Intune to update Microsoft Entra ID, and Conditional Access restores the user’s access to corporate resources.
This mitigates risk to the organization by ensuring attackers who might be in control of these devices can't access corporate resources, while minimizing the impact on user productivity to minimize disruption of business processes.

## Microsoft Security Graph

Microsoft Graph provides a unified programmability model that you can use to access the data in Microsoft 365, Windows, and Enterprise Mobility + Security. You can use the data in Microsoft Graph to build customized apps for your organization.
The Microsoft Graph API offers a single endpoint (https://graph.microsoft.com). You can use REST APIs or SDKs to access the endpoint and build apps that support Microsoft 365 scenarios. Microsoft Graph also includes a powerful set of services that manage user and device identity, access, compliance, and security and help protect organizations from data leakage or loss.

For Security Operations Analysts, both Microsoft Graph API versions support advanced hunting using the runHuntingQuery method. This method includes a query in Kusto Query Language (KQL).

Advanced hunting example in Microsoft Defender XDR:

``
POST https://graph.microsoft.com/v1.0/security/runHuntingQuery
{
    "Query": "DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}
``

![image](https://github.com/user-attachments/assets/bbc31b39-9074-449e-aa18-6853aff3acde)

# Investigating incidents using Sentinel/XDR

![image](https://github.com/user-attachments/assets/d2e88506-3d36-4447-86f9-a81ebb4d7b92)

![image](https://github.com/user-attachments/assets/20213cc9-4033-4ac9-94a4-dd571256e873)

![image](https://github.com/user-attachments/assets/b244e6ec-6559-4896-b715-ea00fc7da48e)

![image](https://github.com/user-attachments/assets/eadbd8a8-d710-493a-8d0c-071d2cd9d8a3)

![image](https://github.com/user-attachments/assets/f3a95c7d-05f9-471e-a499-1486740ae268)

![image](https://github.com/user-attachments/assets/696b5b5c-629e-4416-8ea8-3705ac893096)


# Knowledge Check
1. Which Microsoft Defender XDR solution can detect an Active Directory Domain compromise?
   ANS: **Microsoft Defender for Identity**

2. Which Microsoft Defender XDR solution can detect a phishing email?
   ANS: **Microsoft Defender for Office 365**

3. Which Microsoft Defender XDR solution can detect a malware installation?
   ANS: **Microsoft Defender for Endpoint**








