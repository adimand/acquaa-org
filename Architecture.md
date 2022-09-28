We're building Acquaa based on the principles of [Hexagonal Architecture](http://wiki.c2.com/?HexagonalArchitecture) around a few loosely coupled, highly cohesive services in their own bounded context. Services are aligned with business capabilities. They follow the dependency inversion principle which enables us to choose sensible architectural patterns.

_Please note that this is evolving as we build out the product._

[[https://github.com/acquaa-org/acquaa/blob/gh-pages/images/acquaa_architecture.png|Acquaa Architecture]]

1. Users are signed up by Acquaa and managed on Auth0. They access the system using http over TLS.
2. TLS terminates over an ALB-fronted reverse proxy (NGinx), that sends traffic to different services via an internal load balancer.
3. The internal load balancer delegates requests to available services which are deployed in an active-active fashion across availability zones.
4. Amazon SQS and SNS provide integration and notification capabilities between services.
5. Service logs are collected using CloudWatch in S3 and can be analysed using Insights and Athena.
6. We will maintain periodic snapshots of the databases and also replicate to the DR region.
7. Testers/Partners use a separate sandbox environment to test integration.

**Notes:**
- Currently, the primary VPC is in `us-east-1`(N. Virginia) and the DR is slated to be in `us-west-2`(Oregon).
- The application supports multiple tenants and data is isolated by tagging the organization.
- Communication is over https.
- Data is encrypted at rest and in transit. Data that is encrypted at rest includes the underlying storage for DB instances, its automated backups, read replicas, and snapshots.
- As Auth0 is our identity provider, we are able to support the following [enterprise identity providers](https://auth0.com/docs/authenticate/identity-providers/enterprise-identity-providers).