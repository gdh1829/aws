---
TItle: Elastic Beanstalk
---

# Elastic Beanstalk

## Overview

- Platform-as-a-service
- allows you to quickly deploy and manage applications in the AWS Cloud without worrying about the infrastructure that runs those applications
- automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring for your applications
- supports the following web containters
  - Tomcat, Passenger, Puma
- supports Docker containers
- Workflow
  - `Create Application` -> `Upload Version` -> `Launch Environment` -> `Manage Environment`
- applcation's domain name format:
  - _subdomain.region_.elasticbeanstalk.com
- To relay trace data from your application to AWS X-Ray, you can run the X-Ray daemon on your Elastic Beanstalk environment's Amazon EC2 instances. 
  - Elastic Beanstalk platforms provide a configuration option that you can set to run the daemon automatically.
  ![eb-enable-xray.png]
  - You can enable the daemon in a configuration file in your source code or by choosing an option in the Elastic Beanstalk console.
    - enable the X-Ray daemon by including the `xray-daemon.config` configuration file in the `.ebextentions` directory of your source code, just as shown above. 
  - When you enable the configuration option, the daemon in installed on the instance and runs as a service.

[eb-enable-xray.png]: ./images/eb-enable-xray.png