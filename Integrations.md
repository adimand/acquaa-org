## Integrations to internal systems (e.g. asset management systems)
To integrate with internal systems, the options we propose (in order of preference)

1. Expose APIs to provide this information
2. Send events/messages to a callback URL(webhook)
3. Custom integration with the system (this is time-consuming and expensive as we'll need to get an insight and access into the customer's internal systems). If done, it will most likely be through a proxy fronting the internal system.


## Data Import (e.g. master data):
- Expose APIs to import this data into Acquaa.
- For bulk data, best expressed as a file (e.g., GIS data), we can use SFTP to push/pull required information.

## Logs & Reports:
- Audit logs for user actions will be provided within the app
- Offline reports generated via the system
- Logs to azure sentinel