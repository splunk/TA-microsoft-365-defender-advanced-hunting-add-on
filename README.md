# MS Defender for Endpoint Advanced Hunting Add-on for Splunk

## Installation

Use the Splunk Add-on for Microsoft Cloud Services or Microsoft Azure Add-on for Splunk to ingest data.   
When setting the sourcetype/source choose either:
* Source: azure_event_hub://Defender_Security_Center
* Sourcetype: ms:defender:advancedhunting

## Data Models

Endpoint Data Model Compatibility:

| Dataset | Category | Status |
|---|---|---|
| Ports |  |  |
| Processes | AdvancedHunting-DeviceProcessEvents | Completed |
| Services |  |  |
| Filesystem |  |  |
| Registry |  |  |
