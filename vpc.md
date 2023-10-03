VPC
---

## Internet Gateway

### egress-only internet gateway
- a horiznetally scaled, redundant, and highly available VPC Component that allows outbound communication over IPv6 from instances in your VPC to the internet and **prevents it from initiating an IPv6 connection with your instances.**
- NAT Gateway와 구분: IPv6를 IPv4로 통역해주는 기능이 있는 것이지, 인바운드 IPv6 트래픽이 인스턴스에 도달하도록 막아주는 것은 아니다.

## NAT gateway
- has a NAT64 feature that translates an IPv6 address to IPv4.
- 