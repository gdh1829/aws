ASG - Auto Scaling Group
---

scaling policy
- Predictive
  - Predictive 스케일링 정책은 ASG의 모든 인스턴스가 균일한 capacity를 갖고 있다는 것을 전제로 한다. (t3 1대와 m6 1대의 수용량은 분명 다르지만 그런 것은 고려하지 않는다는 것. 그냥 개별 1대인 것) 즉, 만약 다양한 사이즈와 타입의 EC2를 사용하고 있다면 예측된 공급량은 부정확할 수 있다.
- Scheduled
- Dynamic

