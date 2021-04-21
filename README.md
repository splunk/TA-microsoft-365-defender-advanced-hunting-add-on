# MS Defender for Endpoint Advanced Hunting Add-on for Splunk

## Introduction

This add-on provides field extractions and CIM compatibility for the Endpoint datamodel for Microsoft Defender for Endpoint Advanced Hunting data.

## Installation

Use the Splunk Add-on for Microsoft Cloud Services or Microsoft Azure Add-on for Splunk to ingest data.   
Pick one of these two apps to ingest the data:
* Splunk Add-on for Microsoft Cloud Services (https://splunkbase.splunk.com/app/3110/)
* Microsoft Azure Add on for Splunk (https://splunkbase.splunk.com/app/3757/)

When setting the sourcetype/source choose either:
* Source: azure_event_hub://Defender_Security_Center (If using Microsoft Azure Add-on for Splunk)
* Sourcetype: mscs:azure:eventhub:defender:advancedhunting (If using Splunk Add-on for Microsoft Cloud Services)


## Data Models

Endpoint Data Model Compatibility:

| Dataset | Category | Status |
|---|---|---|
| Ports | AdvancedHunting-DeviceNetworkEvents | Completed |
| Processes | AdvancedHunting-DeviceProcessEvents | Completed |
| Services |  | N/A |
| Filesystem | AdvancedHunting-DeviceFileEvents | Completed |
| Registry | AdvancedHunting-DeviceRegistryEvents | Completed |

Schema reference: https://docs.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-schema-tables?view=o365-worldwide

## Support

This add-on is provided without official support, but is supported on a best-effort basis by the community.  
Contributions and pull requests are more than welcome.
Official Git repo: https://github.com/inspired/TA-microsoft-defender-for-endpoint-advanced-hunting-add-on-for-splunk

## Contact

Authored by Mikael Bjerkeland (mbjerkeland@splunk.com)
