
# Microsoft 365 Defender Advanced Hunting Add-on for Splunk

## Introduction

This add-on provides field extractions and CIM compatibility for the Endpoint datamodel for Microsoft 365 Defender Advanced Hunting data.   
The data is similar in content to Sysmon data and can be used by Detection Searches in i.e. Splunk Enterprise Security Content Update.   

Future versions will include support for Microsoft Defender for Office 365, Microsoft Defender for Identity and other products in the Microsoft 365 suite.

## Installation

1. Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to an Azure Event Hub:
   *  https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/raw-data-export-event-hub?view=o365-worldwide

2. Install this add-on on your Search Heads and Indexers

3. Install and use one of these two Splunk add-ons to ingest the data:
   * Splunk Add-on for Microsoft Cloud Services (https://splunkbase.splunk.com/app/3110/)
   * Microsoft Azure Add on for Splunk (https://splunkbase.splunk.com/app/3757/)

4. When setting the sourcetype/source choose either:
   * Sourcetype: `mscs:azure:eventhub:defender:advancedhunting` (If using Splunk Add-on for Microsoft Cloud Services)
   * Source: `azure_event_hub://Defender_Security_Center` (If using Microsoft Azure Add-on for Splunk)

5. Test that data is arriving by running the following search: `index=* eventtype="ms_defender_advanced_hunting_sourcetypes"`

## Data Models

Data Model Compatibility:

| Product | Dataset | Category | Status |
|---|---|---|---|
| MS Defender for Endpoint | Endpoint.Ports | AdvancedHunting-DeviceNetworkEvents | Completed |
| MS Defender for Endpoint | Endpoint.Processes | AdvancedHunting-DeviceProcessEvents | Completed |
| MS Defender for Endpoint | Endpoint.Services | N/A |
| MS Defender for Endpoint | Endpoint.Filesystem | AdvancedHunting-DeviceFileEvents | Completed |
| MS Defender for Endpoint | Endpoint.Registry | AdvancedHunting-DeviceRegistryEvents | Completed |

Schema reference: https://docs.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-schema-tables?view=o365-worldwide

## Data Samples

So how does this data look like when it's ingested into Splunk? Prettified, of course:

```json
{
  "time": "2021-04-14T18:50:42.1532345Z",
  "tenantId": "4a653e38-cdfe-1337-beef-abcdefabcdef",
  "operationName": "Publish",
  "category": "AdvancedHunting-DeviceProcessEvents",
  "properties": {
    "ProcessVersionInfoCompanyName": "Microsoft Corporation",
    "ProcessVersionInfoProductName": "Microsoft® Windows® Operating System",
    "ProcessVersionInfoProductVersion": "10.0.18362.1",
    "ProcessVersionInfoInternalFileName": "whoami.exe",
    "ProcessVersionInfoOriginalFileName": "whoami.exe",
    "ProcessVersionInfoFileDescription": "whoami - displays logged on user information",
    "ProcessIntegrityLevel": "System",
    "AccountSid": "S-1-5-18",
    "LogonId": 999,
    "AccountName": "system",
    "AccountDomain": "nt authority",
    "AccountUpn": null,
    "AccountObjectId": null,
    "ProcessTokenElevation": "TokenElevationTypeDefault",
    "ProcessCreationTime": "2021-04-14T18:49:17.528333Z",
    "ProcessId": 40288,
    "FileName": "whoami.exe",
    "ProcessCommandLine": "\"whoami.exe\" /user",
    "FolderPath": "C:\\Windows\\System32\\whoami.exe",
    "FileSize": 71168,
    "MD5": "2eeeec89e705f73ffbcae014e1828788",
    "SHA256": "a8a4c4719113b071bb50d67f6e12c188b92c70eeafdfcd6f5da69b6aaa99a7fd",
    "SHA1": "8f1f9e265911956c7f8f3861c34def9b8fa63813",
    "AdditionalFields": null,
    "InitiatingProcessVersionInfoCompanyName": "Microsoft Corporation",
    "InitiatingProcessVersionInfoProductName": "Microsoft® Windows® Operating System",
    "InitiatingProcessVersionInfoProductVersion": "10.0.18362.1",
    "InitiatingProcessVersionInfoInternalFileName": "POWERSHELL",
    "InitiatingProcessVersionInfoOriginalFileName": "PowerShell.EXE",
    "InitiatingProcessVersionInfoFileDescription": "Windows PowerShell",
    "InitiatingProcessSignatureStatus": "Valid",
    "InitiatingProcessSignerType": "OsVendor",
    "InitiatingProcessFolderPath": "c:\\windows\\system32\\windowspowershell\\v1.0\\powershell.exe",
    "InitiatingProcessFileSize": 451584,
    "InitiatingProcessMD5": "cda48fc75952ad12d99e526d0b6bf70a",
    "InitiatingProcessSHA256": "908b64b1971a979c7e3e8ce4621945cba84854cb98d76367b791a6e22b5f6d53",
    "InitiatingProcessSHA1": "36c5d12033b2eaf251bae61c00690ffb17fddc87",
    "InitiatingProcessLogonId": 999,
    "InitiatingProcessAccountSid": "S-1-5-18",
    "InitiatingProcessAccountDomain": "nt authority",
    "InitiatingProcessAccountName": "system",
    "InitiatingProcessAccountUpn": null,
    "InitiatingProcessAccountObjectId": null,
    "InitiatingProcessCreationTime": "2021-04-14T18:49:15.9040226Z",
    "InitiatingProcessId": 39240,
    "InitiatingProcessFileName": "powershell.exe",
    "InitiatingProcessCommandLine": "\"powershell.exe\" -executionPolicy bypass -file  \"C:\\Program Files (x86)\\Microsoft Intune Management Extension\\Content\\DetectionScripts\\7bdb56a9-0db0-4fd3-a373-4a50613270bc_1.ps1\" ",
    "InitiatingProcessParentCreationTime": "2021-04-14T18:49:15.6500648Z",
    "InitiatingProcessParentId": 42028,
    "InitiatingProcessParentFileName": "AgentExecutor.exe",
    "InitiatingProcessIntegrityLevel": "System",
    "InitiatingProcessTokenElevation": "TokenElevationTypeDefault",
    "DeviceId": "df5b716f594eb30d61bf2b73998fea62a9b448e3",
    "AppGuardContainerId": "",
    "MachineGroup": null,
    "Timestamp": "2021-04-14T18:49:17.7849324Z",
    "DeviceName": "bobslaptop.example.com",
    "ReportId": 30779,
    "ActionType": "ProcessCreated"
  }
}
```
## Support

This add-on is provided without official support, but is supported on a best-effort basis by the community.  
Contributions and pull requests are more than welcome.   
Official Git repository: https://github.com/inspired/TA-microsoft-365-defender-advanced-hunting-add-on-for-splunk

## Contact

Authored by Mikael Bjerkeland (mbjerkeland@splunk.com)
