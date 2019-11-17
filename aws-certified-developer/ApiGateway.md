---
Title: API Gateway
---
# API Gateway

- API caching feature
  - how to enable caching feature
  ![apigateway-cache-invalidation.png]
  - What if a client of your API can invalidate an existing cache entry and reload it from the integration endpoint for individual reqeusts? The client must send a request that contains the `Cache-Control: max-age=0` header. ※`Cached: false` is a custom header.
  - The client receives the reponse directly from the integration endpoint instead of the cache, provided that the client is authorized to do so. This replaces the existing cache entry with the new response, which is fetched from the integration endpoint.
  - `Allowing the client to access the endpoint directly` is incorrect because the purpose of placing API Gateway in-front of your endpoint is to not expose your endpoints to the public and risk security issues. It also provides you the additional benefits of not burdening your endpoints with a massive number of requests and allowing developer-friendly data exchanges through APIs.

You have several API Gateway APIs with Lambda Integration for each release life cycle of your application. There is requirement to consolidate multiple releases into a single API Gateway for the ALPHA, BETA, RC (Release Candidate), and PROD releases. For example, their clients can connect to their ALPHA release by using the `alpha.dev.com` endpoint and beta release through the `beta.dev.com` endpoint.
As the AWS developer, how you can satisfy this requirement?
- Set up Stage Variables for each release.

[apigateway-cache-invalidation.png]: ./images/apigateway-cache-invalidation.png