we have few ms for this app:

- IAM (ms using a db)
- userDetails: (ms using db)
  * basic user details as addresses, phone, mails etc.
  * past jobs
  * income history
- searchBox (will be included in th userDetails ms due to similar functionality)
- ID validation (ms)

Patterns I Chose:
Microservices - Business Capabilities: I chose this pattern due to the simplicity of the system. First, there's the IAM responsibility; second, there is the user, who is the main actor in the system, so they get an independent microservice to handle all data and searches. Finally, the main functionality of the system is the ID validation, which may interact with third-party applications like the government.

Database per Service: I believe the most important issue for a banking system is to secure customer data. Regarding the sketch of the system above, I would separate the IAM database and the UserDetails database, even though I’ll probably have to duplicate some of the user's information.

Observability Patterns: For this specific system, if I had to pick only one pattern, I believe the most relevant is the Health Check pattern. When dealing with a banking system, the most important matter is the bank's reputation. With that said, I believe the system should have minimal downtime, and whenever that happens, I want to be able to monitor this as soon as possible.

