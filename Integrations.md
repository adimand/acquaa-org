## Integrations to internal systems (e.g. asset management systems)

### General API Integration Pattern
[[https://github.com/acquaa-org/acquaa/blob/gh-pages/images/api_integration.png|General API Integration Pattern]]

To integrate with internal systems, the options we propose (in order of preference)

1. Expose APIs to provide this information
   - secured via an API key or JWT.
   - API will also allow updates to certain resources (e.g. internal identifiers)
   - subject to rate limitations.
   - SLAs will be clearly defined and upgrades/outages clearly communicated.
2. Send events/messages to a callback URL(webhook)
   - customer exposes an API endpoint where Acquaa can send events as they occur.
   - event contract will be published.
   - secured via an API key or JWT.
   - failures will be retried thrice at exponentially increasing times (configurable).
3. Custom integration with the system (this is time-consuming and expensive as we'll need to get an insight and access into the customer's internal systems). If done, it will most likely be through a proxy fronting the internal system.

## Data Import
- Expose APIs to import this data into Acquaa (e.g. master data like equipment type, sizes etc.).
- For bulk data, best expressed as a file (e.g. GIS data), we can use SFTP to push/pull required information.

[[https://github.com/acquaa-org/acquaa/blob/gh-pages/images/sftp.png|SFTP Diagram]]

## Logs & Reports
- Audit logs for user actions will be provided within the app.
- Offline (bulk) reports can be generated via the system.
