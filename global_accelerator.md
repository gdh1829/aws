AWS Global Accelerator
---

- 퍼블릭 애플리케이션의 가용성, 성능 및 보안을 개선하는데 유용한 네트워킹 서비스로서, 애플리케이션의 고정 진입점(fixed entry point) 역할을 하는 두 개의 글로벌 static 공용 IP(ex. ALB, NLB, EC2 인스턴스 및 Elastic IP)를 제공.
- AWS 글로벌 인프라의 성능, 보안 및 가용성을 활용하여 Global Accelerator 엣지 로케이션 중 하나에 사용자 트래픽으르 온보드 할 수 있다. 사용자는 static ip 주소를 통해 애플리케이션 엔드포인트에 액세스할 수 있으므로 DNS와 별개로 경로 지정이 확정된다는 이점이 있다.