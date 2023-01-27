## Integrations to internal systems (e.g. asset management systems)

To integrate with the customer's internal systems, we propose the following options:

#### Option 1: Acquaa exposes APIs and the customer hosts a client app that will be the interface between our APIs and their internal system(s).

- Communication can work with the following ways:
  1. The client can call Acquaa to update their data or pull information out.
  2. Business events can be sent to a client API endpoint (e.g. webhook) and can be used to update their systems.
     * Event contracts will be published by Acquaa.
     * Customer exposes an API endpoint where Acquaa can send events as they occur.
- Development/deployment of client app into the customer's data centre.
- In case of we agree to use a webhook URL to publish events, there will be some customer-side development too.

[[https://github.com/acquaa-org/acquaa/blob/gh-pages/images/option_1_api_integration.png|Option 1]]

#### Option 2: Acquaa builds and hosts a client app to interface with the customer's internal system(s).

- Customer has to expose the system to the outside world - with appropriate security mechanisms in place.
- Custom integration per client can take time as we need insights into their system(s).
- Development/deployment of client app into Acquaa's data centre.

[[https://github.com/acquaa-org/acquaa/blob/gh-pages/images/option_2_api_integration.png|Option 2]]

**For all the options,**
- Communication is preferred via APIs.
- Secured via an API key/JWT/Basic Auth.
- Acquaa API will allow updates to certain resources (e.g. internal identifiers, master data for the organisation).
- Subject to rate limitations.
- API failures will be retried thrice at exponentially increasing times (configurable).
- The API calls can be synchronous or asynchronous based on the process.
- SLAs will be clearly defined and upgrades/outages clearly communicated from both sides.
- Escalation channels in case of issues will be established.

## Data Import
- Expose APIs to import this data into Acquaa (e.g. master data like equipment type, sizes etc.).
- For bulk data, best expressed as a file (e.g. GIS data), we can use SFTP to push/pull required information.

[[https://github.com/acquaa-org/acquaa/blob/gh-pages/images/sftp.png|SFTP Diagram]]

## Logs & Reports
- Audit logs for user actions will be provided within the app.
- Offline (bulk) reports can be generated via the system.
- System (network/security) logs will be retained for 7 years but will be available for immediate access only for 3 years.
- Application logs will be retained for 30 days and then moved to offline storage. These will be deleted after a year.
- Application audit logs will be accessible as long as the app is available.
