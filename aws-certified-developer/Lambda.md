Lambda Related
---

## Networks

### Private Subnets for Lambda in VPC 
- Recommended that you dedicate the private subnets exclusively for your lambda functions and keep them seperate from subnets used by your ec2 instances

### When your lambda function needs Internet access in VPC
- Do not attach it to a public subnet or to a private subnet without Internet access.
- Instead, attach it only to private subnets with Internet access through a NAT instance or add a NAT gateway to your VPC.
- You should also ensure that the associated security group of the Lambda function allows outbound connections like 0.0.0.0./0

### Step in order for your Lambda function to be integrated with your VPC
- if you choose which VPC to be set with Lambda, it is already done automatically by AWS Lambda to Set up ENIs(elastic network interfaces) to enable your Lambda function to connect securely to other resources within your private VPC.
- Nothing to do for the step.