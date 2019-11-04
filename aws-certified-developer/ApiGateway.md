API Gateway
---

You have several API Gateway APIs with Lambda Integration for each release life cycle of your application. There is requirement to consolidate multiple releases into a single API Gateway for the ALPHA, BETA, RC (Release Candidate), and PROD releases. For example, their clients can connect to their ALPHA release by using the `alpha.dev.com` endpoint and beta release through the `beta.dev.com` endpoint.
As the AWS developer, how you can satisfy this requirement?
- Set up Stage Variables for each release.