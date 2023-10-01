RDS Aurora
---

## lambda function invoke native feature
- 오로라 클러스터의 native function 또는 stored procedure을 통해, AWS 람다 함수를 호출할 수 있다.
- 오로라 데이터베이스의 테이블에 데이터 변경사항이 생길때마다 데이터 변경사항을 켭쳐할 때 유용.
- RDS events와의 차이
  - RDS event는 DB 인스턴스의 operational events, parameter group events, DB security group events, db snapshot events 등 만을 제공하지 데이터 변경사항에 대한 이벤트가 아니다.
