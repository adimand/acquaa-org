_This is a WIP document that serves as an introduction to our tech stack._

We believe in choosing boring(a.k.a battle-tested and stable) technology to build Acquaa. The idea is to maintain a balance between stable, well-documented, well-understood tech while maintaining a modern and efficient developer workflow to solve the problem at hand.

### Backend
- Java, Kotlin, Spring Boot, Axon
- Std testing and linting libs(e.g. Junit, Mockito, PMD etc..)
- Gradle

### User Interface
- NextJS, IBM Carbon
- Std testing and linting libs(e.g. Jest, ESLint etc..)
- Webpack

### Databases
- Postgres (RDS)

### Version Control
- git and Github

### CI/CD
- Services built into docker images and pushed to ECR by Github Actions.

### Deployment
- Deploy onto AWS
- Services deployed as docker containers on EC2 using Ansible.
- Terraform for defining infrastructure.
- EC2 host configuration done by ansible scripts; pulled and applied by cron.

### Third-party Integrations
- Auth0 for authentication and authorisation.
- SendGrid for email notifications.