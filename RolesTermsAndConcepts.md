Roles&Policies Terms and Concepts
---

**AWS service role**  
A role that a service assumes to perform actions in your account on your behalf.  
When you set up some AWS service environments, you must define a role for the service to assume. This service role must include all the permissions required for the service to access the AWS resources that it needs.  
Service roles provide access only within your account and cannot be used to grant access to services in other accounts.  

**AWS service role for an EC2 instance**  
A special type of service role that an application running on a Amazon EC2 instance can assume to perform actions in your account. This role is assigned to the EC2 instance when it is launched. Applications running on that instance can retrieve temporary security credentials and perform actions that the role allows

**AWS service-linked role**  
    A unique type of service role that is linked directly to an AWS service. Service-linked roles are predefined by the service and include all the permissions that the service requires to call other AWS services on your behalf.  
    The linked service also defines how you create, modify, and delete the role. It might allow you to create, modify, or delete the role as part of a wizard or process in the service. Or it might require that you use IAM to create or delete the role. Regardless of the method, service-linked roles make setting up a service easier because you don't have to manually add the necessary permissions.
    ! Note
        If you already using a service when it begins supporting service-linked roles, you might receive an email telling you about a new role in your account. In this case, the service automatically created the service-linked role in your account. You don't need to take any action to support this role, and you should not manually delete it.

**Role chaining**  
    Role chaining occurs when you use a role to assume a second role through the AWS CLI or API. For example, assume that User1 has permission to assume RoleA and RoleB. Additionally, RoleA has permission to assume RoleB. You can assume RoleA by using User1's long-term user credentials in the `AssumeRole` API operation. This operation returns RoleA's short-term credentials. To engage in role chaining, you can use RoleA's short-term credentials to assume RoleB.  
    Role chaining limits your AWS CLI or API role session to a maximum of one hour. When you use the AssumeRole API operation to assume a role, you can specify the duration of your role session with the `DurationSeconds` paramter. You can specify a parameter value of up to 43200 seconds (12 hours), depending on the maximum session duration setting for your role. However, if you assume a role using role chaining and provide a `DurationSeconds` parameter value greater than one hour, the operation fails.  

**Identity-based policies**  
are permissions policies that you attach to an IAM identity, such as an IAM user, group, or role.  
control what actions the identity can perform, on which resources, and under what conditions.  
Identity-based policies can be further categorized:
- **Managed policies**: Standalone identity-based policies that you can attach to multiple users, groups, and roles in your AWS account. You can use two types of managed policies:  
    + **AWS managed policies**: Managed policies that are created and managed by AWS. If you are new to using policies.  
    + **Customer managed polices**: Managed policies that you create and manage in your AWS account. Customer managed policies provide more precise control over your policies than AWS managed policies.
- **Inline policies**: Policies that you create and manage and that are embedded directly into a single user, group, or role. In most cases, AWS doesn't recommend using inline policies.  

**Resource-based policies**  
are permissions policies that you attach to a resource such as an Amazon S3 bucket or an IAM role trust policy.  
control what actions a specified principal can perform on that resource and under what conditions.  
Resource-based policies are inline policies, and there are no managed resource-based policies. To enable cross-account access, you can specify an entire account or IAM entities in another account as the principal in a resource-based policy.  
The IAM service supports only one type of resource-based policy called a role *trust policy*, which is attached to an IAM role. Because an IAM role is both an identity and a resource that supports resource-based policies, you must attach both a trust policy and and identity-based policy to an IAM role. Trust policies define which principal entities(accounts, users, roles, and federated users) can assume the role.


[AWS Reference1](https://docs.aws.amazon.com/en_pv/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-role)
[AWS Reference2](https://docs.aws.amazon.com/en_pv/IAM/latest/UserGuide/introduction_access-management.html#intro-access-resource-based-policies)
[AWS Services That Work with IAM](https://docs.aws.amazon.com/en_pv/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html)