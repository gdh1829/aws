AWS IAM Identity Center (successor to AWS Single Sign-On)
---

- AWS 계정과 클라우드 애플리케이션에 대한 SSO 접근을 제공.
- AWS Directory Service를 통해 MS Active Directory와 연결하여 해당 디렉토리의 사용자가 기존 AD 사용자 이름과 비밀번호를 사용하여 개인화된 AWS access portal에 로그인할 수 있다.
- AWS access portal에서 사용자는 권한이 있는 모든 AWS 계정과 클라우드 애플리케이션에 액세스할 수 있다.
- AD의 자체 관리 디렉토리에 있는 사용자는 AWS access portal에서 AWS 계정 및 클라우드 애플리케이션에 대한 SSO 엑세스 권한도 가질 수 있다.
- AWS Organizations에는 external authentication을 사용할 수 있는 옵션은 없다. 기존 디렉토리를 사용하려면 AWS SSO를 구성해야한다.

## FYI,
- Amazon Cognito는 모바일이나 웹애플리케이션을 위한 SSO에 사용된다. Directory Service 인증을 위한 것이 아님.
- Service Control Policies(SCP)는 organization의 여러 계정에 걸쳐 정책을 제한하거나 구현하려는 경우 사용.