# Clearing Windows Event Logs

- All the events and actions performed on the system is captured and stored in the Windows Event Logs. 
- They can be accessed using Event Viewer on Windows
- Event logs are categorized into:
1. Application Logs : Stores program/app events like crash report, start up etc..
2. System Logs : system start ups, reboots etc..
3. Security Logs : Credential changes, authentication failures etc..

We can clear the entire event log using a single Meterpreter command.

```
clearev
```
