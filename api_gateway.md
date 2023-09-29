API Gateway
---

- API를 배포함에 있어,
  - Canaary release 지원: 일부 포션만 신규 버전으로 노출하여 모니터링 후 퍼포먼스/에러 이슈 등의 문제가 없을시 점점 그 비율을 조정하여 손쉽게 확대해나갈 수 있다.
  - 위와 같은 간단한 Canary 배포를 지원하므로 API Gateway 환경에서는 blue/green 배포 방식은 양쪽의 provisioned and maintained 환경을 만들어야하고 비효율적이다.
