Amazon GuardDuty
---
지능형 위협 탐지 서비스.
- AWS 계정 및 워크로드에서 악의적 활동을 모티러이하고 상세한 보안 조사 결과 제공하여 가시성 및 해결을 촉진하는 위협 탐지 서비스.
- S3, DB, instance, accouts and users, container, serverless 등 지속 감지.
- 머신러닝 비정상 감지, 몰웨어 탐지 등.
- can generate findings based on suspicious activities, such as
  - requests coming from kown malicious IP addresses,
  - changing of bucket policies/ACLs to expose an s3 bucket publicly,
  - suspicious API call patterns that attempt to discover misconfigured bucket permissions.

## FYI, Amazon Macie 서비스와 구분하기
- Macie
  - 머신러닝 기반 s3 내부 데이터의 민감정보에 대한 발견/버호/분류 보안 서비스.
  - 악의적 사용 패턴 감지 서비스가 아님.
- Guardduty
  - AWS 계정 및 워크로드간 악의적 활동 및 해결 촉진 위협 탐지 서비스.
  - 악의적인 행동을 탐지하기 위해 anomaly detection, machine learning, and continuously updated threat intelligence와 조합하여 사용.
- Amazon Inspector
  - AWS에 배포된 애플리케이션의 보안과 컴플라이언스 향상을 돕기 위한 자동화된 시큐리티 assessment 서비스.
