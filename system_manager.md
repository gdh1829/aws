AWS System Manager
---

## Parameter Store
- 설정 데이터와 시크릿 관리를 위한 secure, hierarchical 스토리지.
- 비밀번호, 데이터베이스 strings, EC2 Instance IDs, AMI Ids, 라이센스 코드 등을 paramter values로서 보관 가능.
- 값을 plain text(Type: String)나 encrypted data(Type: SecureString)로 보관 가능.
- 파라미터를 생성할때 지정한 유니크한 이름을 통하여 참조 가능.
- Parameter Store parameters에 대한 참조를 지원하는 다른 AWS 서비스를 사용할때 Secret Manager secrets를 검색할 수도 있음.
- Secret Manager와 비교
  - 시크릿 매니저에 암호화된 데이터를 보관해둘 수도 있지만, 이 경우 비용이 청구되므로 일반적인 애플리케이션 파라미터라면 System Manager Parameter Store를 이용하는 편이 합리적.

## OpsCenter
