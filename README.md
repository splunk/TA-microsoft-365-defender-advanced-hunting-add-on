# MS Defender for Endpoint Advanced Hunting Add-on for Splunk

## Installation

Use the Splunk Add-on for Microsoft Cloud Services or Microsoft Azure Add-on for Splunk to ingest data.   
When setting the sourcetype/source choose either:
* Source: azure_event_hub://Defender_Security_Center
* Sourcetype: ms:defender:advancedhunting

TODO: Find the right source for the MS Cloud Services Addon and add to props.conf and eventtypes.conf

## Data Models

Endpoint Data Model Compatibility:

| Dataset | Category | Status |
|---|---|---|
| Ports | AdvancedHunting-DeviceNetworkEvents | Completed |
| Processes | AdvancedHunting-DeviceProcessEvents | Completed |
| Services |  | N/A |
| Filesystem | AdvancedHunting-DeviceFileEvents | Completed |
| Registry | AdvancedHunting-DeviceRegistryEvents | Completed |
