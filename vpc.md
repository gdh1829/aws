VPC
---

## peering connection
- 두 VPC 망을 연결해주는 기능.
- on-premise 와의 연결 X. 그런 경우는 AWS Direct connection 사용.
- **단, VPC peering connection은 edge to edge 라우팅을 지원하지 않는점 명심!!**
  - peering 관계에 있는 VPC가 다음 여러 커낵션 중 하나에 해당하는 경우, 피어링 관계를 확장할 수 없다.
    - VPN connection or AWS Direct Connection connection to a corporate network.
    - Internet connection to private subnet through a NAT device.
    - s3 endpoint와 같은 AWS service에 대한 gateway vpc endpoint.
    - IPv6 클래식링크 connection. linked EC2-Classic과 반대편 peering connection VPC의 인스턴스 간 IPv4 통신을 활성활 할 수 있지만, EC2-Classic에서는 IPv6가 지원되지 않으므로 이 연결을 IPv6 통신을 위해 확장 불가.

## endpoint service
- has two types: gateway endpoint and interface endpoint.
### gateway endpoint
- 인터넷 게이트웨이나 NAT 디바이스 없이 신뢰성 있는 엔드포인트 커넥션 제공.
- VPC의 인스턴스는 Public IP가 불필요.
- supported resources
  - to Amazon S3
  - to DynamoDB
  - not others. others have interface endpoint.
- endpoint policy 지원
  - 연결 가능한 접근 서비스 정책.
  - IAM 유저 정책이나 service-specific(ex, s3 bucket policies) 정책를 오버라이드 하거나 대체하지 않는다. 특정 서비스에 대한 엔드포인트로의 접근 제한을 위한 별도의 정책이다.
  - **S3 버킷에 대한 접근 정책을 설정하는데 있어 bucket policy는 개별 버킷에 대한 정책이므로 일일이 모두 설정해주어야 하지만, gateway endpoint to S3 하나면 간편하게 whitelist 관리 제한 가능**
### interface endpoint

## Internet Gateway
- vpc가 외부 인터넷과 연결될 수 있도록 하는 통로 게이트웨이.

### egress-only internet gateway
- a horiznetally scaled, redundant, and highly available VPC Component that allows outbound communication over IPv6 from instances in your VPC to the internet and **prevents it from initiating an IPv6 connection with your instances.**
- NAT Gateway와 구분: IPv6를 IPv4로 통역해주는 기능이 있는 것이지, 인바운드 IPv6 트래픽이 인스턴스에 도달하도록 막아주는 것은 아니다.

## NAT gateway
- has a NAT64 feature that translates an IPv6 address to IPv4.

## Virtual Private Gateway
![emr](./images/virtual_private_gateway.png)
- 기본적으로 VPC에 인스턴스를 띄우게 되면 자체 네트워크(ex, on-premises)와 통신할 수 없기에, Virtual Private Gateway를 VPC에 붙이고 커스텀 라우팅 테이블을 만들고 시큐리티 그룹룰도 설정하고 AWS Managed VPC connection도 생성해야한다.
  - AWS에서 VPC Connection 용어의 의미는 VPC와 자체 네트워크 간의 커넥션을 일컫는다.
  - AWS는 인터넷 프로토콜 시큐리티(IPsec) VPN connections를 지원.
  - customer gateway는 고객의 자체 네트워크 사이드의 물리적 디바이스나 소프트웨어 애플리케이션을 일컫음.

## AWS Transit Gateway
- 트랜짓 게이트웨는 중앙 허브를 통해 VPCs와 on-premises 네트워크를 연결하는데 사용된다.