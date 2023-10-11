AWS DMS - Database Migration Service
---

- DMS는 **다운타임 없이** 데이터베이스를 AWS로 마이그레이션할 수 있도록 돕는다.
- 마이그레이션 동안 소스 데이터베이스에서 발생하는 모든 데이터 변경사항은 지속적으로 타겟으로 복제가 되며, 소스 데이터베이스는 마이그레이션이 진행되는 동안 fully operational 하다.
- `One-time migration` or `ongoing replication`
  - 원타임 마이그레이션 또는 지속적 복제에 대한 DMS 작업을 설정할 수 있다.
  - ongoin replication은 소스와 타겟 데이터베이스가 계속 동기화될수 있도록 한다. 일단 셋업되면 낮은 지연시간으로 소스의 변경사항을 타겟으로 계속 적용한다.
