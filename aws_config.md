AWS Config
---

- AWS 리소스의 설정들에 대하여 assess, audit, and evaluate 가능하게 하는 서비스.
- Config는 지속적으로 AWS 리소스의 설정을 모니터하고 기록하여 원하는 구성과 비교하여 자동으로 평가할 수 있다.
- Config를 통하여, 아마존 리소스간의 관계와 설정 변화에 대해 리뷰하고 디테일한 리소스 설정 변경 히스토리를 자세하게 들여다보고 내부 지침에 지정된 구성에 대한 전반적인 규정 준수를 결정할 수 있다.
- 이를 통해 감사 준수, 보안 분석 변경 관리, 운영 트러블슛팅 등을 간편하게 한다.

## Config rule
- Config Rule 생성을 통해 AWS 계정의 이상적 설정을 강제할 수 있다.
- 또한 룰에 위한한 설정들에 대해서도 체크가 가능.

## Config Dashboard
- Rule과 리소스 상태에 대한 규정 준수 상태를 확인 가능

## FYI,
- Trusted Advisor 서비스는 Best Practice Recommendation만 제공하며 rule 기능은 없다.
- CloudTrail도 AWS 리소스 변경 히스토리에 대해 기록하지만, Config rule처럼 강제할 수 있는 rule을 만들 수는 없다.