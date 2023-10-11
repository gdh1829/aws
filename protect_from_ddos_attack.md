Protect your system from DDoS attack
---

You can do the following:
- Use an Amazon CloudFront service for distributing both static and dynamic content.
- Use an ALB with Auto Scaling groups for your EC2 instances. Prevent direct Internet traffic to your Amazon RDS database by deploying it to a new private subnet.
- Set up alerts in Amazon CloudWatch to look for high `Network In` and CPU utilization metrics.

ELB, EC2와 같은 AWS Regional 서비스들의 디도스 회복성
CloudFront, WAF, Route53, API Gateway와 같은 AWS Edge location 서비시들은 엣지 로케이션의 글로벌 네트워크(내결함성과 더 큰 볼륨의 트래픽 스케일 제공) 이용 이점 제공.  

AWS Shield and AWS WAF
- 클라우드 네트워크 강화를 도움.
- Shield: 스탠다드와 어드밴스드 두 티어의 매니지드 디도스 공격 보호 서비스
  - Standard: always-on detection and inline mitigation techniques
    - ex. 결정론적(deterministic) 패킷 필터링, priority-based traffic shaping to minimize application downtime and latency.
  - Advanced: 모드 사용시 WAF 무료.
- WAF: 웹 애플리케이션 방화벽
- 