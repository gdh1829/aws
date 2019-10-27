AssumeRole
---

Returns a set of temporary security credentials(here and after TSC) that you can use to access AWS resources that you might not normally have access to. These temporaray credentials consist of an access key ID, a secret key, and a security token. Typically, you use AssumeRole within your account or for cross-account access.  

! Important  
You cannot use AWS account root user credentials to call AssumeRole but an IAM user or an IAM role

For cross-account access, you could create long-term credentials in each account to access those resources but managing all those credentials and remembering which one can access which account can be time consuming.  
Istead, you can create one set of long-term credentials in one account. Then use TSC to access all the other accounts by assuming roles in those accounts.  

By default, the TSC created by AssumeRole last for one hour. However, you can use the optional DurationSeconds paramter to specify the duration of your session ranging from 900 seconds(15 minutes) up to the maximum session duration setting for the role. The maximum session duration limit applies when you use the AssumeRole* API operations or the assume-role* CLI commands.  However the limit does not apply when you use those operations to create a console URL.  

The TSC created by AssumeRole can be used to make API calls to any AWS service with the following exception: You cannot call the AWS STS `GetFederationToken` or `GetSessionToken` API operations.  

To assume a role from a different account, your AWS account must be trusted by the role. The trust relationship is defined in the role's trust policy when the role is created. That trust policy states which accounts are allowed to delegate that access to users in the account.  

A user who wants to access a role in a different account must also have permissions that are delegated from the user account administrator. The administrator must attach a policy that allows the user to call `AssumeRole` for the ARN of the role in the other account. If the user is in the same account as the role, then you can do either of the following:  
- Attach a policy to the user (identical to the previous user in a different account).  
- Add the user as principal directly in the role's trust policy.  

In this case, the trust policy acts as an IAM resource-based policy. Users in the same account as the role do not need explicit permission to assume the role.  

AssumeRole - Cross-Account Delegation and Federation Through a Custom Identity Broker  

AssumeRole API operation is useful  
- for allowing existing IAM users to access AWS resources that they don't already have access to, such as resources in another AWS account.  
- as a means to temporarily gain privileged access, for example, to provide multi-factor authentication (MFA).  

[AWS Reference](https://docs.aws.amazon.com/en_pv/STS/latest/APIReference/API_AssumeRole.html)